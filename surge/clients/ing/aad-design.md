<!-- markdownlint-disable first-line-h1 first-header-h1 -->
<!-- cSpell:word permissioning kbrubaker multitenancy multitenant -->
<!-- cSpell:ignore surgeforward iisnode adal msft azman -->

*[Home](../../..) > [Surge](../../index.md)* > Clients > ING

# Azure AD Permissioning Questions

I have a task to provide application level permissioning for a Surge
Client in an Azure environment. Please let me know if you can help.
Here's how to contact me:

- Surge Slack DM: @kbrubaker
- Surge Email: kbrubaker@surgeforward.com

## Requirements

Here are the requirements:

- Needs to work in the application architecture, where:
  - Services are hosted in Azure
  - Back end API is WebAPI 2 using .NET 4.7 and VS2017
  - Database is Azure Cosmos DB with MongoDB bindings
  - UI is Angular 4 served by a NodeJS service using `iisnode`
  - UI is already using Azure AD for authentication through [ADAL][aad-adal]
- Client is pretty much out of money so we need to minimize development time
- The Client's own staff will authenticate through the application's Azure
  AD
- The application needs to work with multiple tenants of their own B2B clients
- They need to integrate with the Azure AD of one of their government clients
- They also want to have commercial clients/tenants, so social media account
  authentication also will need to be supported
- The user space is small with tens of client with tens of users, often
  under 10 users per client.

## Options

I have found a bewildering array of Azure authentication/authorization
services including:

- Azure AD Security Groups
- Azure AD [AppRoles][aad-app-roles]
- Azure AD [v2.0 endpoint][aad-v2]
- Azure AD [B2B][aad-b2b]
- Azure AD [B2C][aad-b2c]
- Azure AD [Connect][aad-connect]
- Azure AD [Graph API][aad-graph]
- Microsoft [Graph API][msft-graph]

Many of these have separate and additional costing, architecture, and configuration.

I know that `ADAL` gives us a traditional OAuth2 token-based authorization
model, but I'm unclear how to best extend that to a permissions-based
authorization model that will support all the requirements with minimal
time and recurring cost.

## What I want

Back in the day Microsoft had a technology called [AzMan][win-azman]
that support fine grain Role Based Access Control (RBAC) for
applications. Unfortunately it had several limitations. However the
model of `User ⇒ Role/Group ⇒ Permission` where the application
permissions are not AD Security Groups is a good one for many applications
and one I've set up for several large Enterprise application architectures
over the years.

With the advent of ClaimsPrincipal and JWT, I've incorporated permissions
into claims-based authorization. Just as app permissions should not me
Windows Security Groups, which enlarges the Windows security token, so
also, I believe these fine-grained permissions are better not included as
part of the JWT token, but rather application provided.

In the end, though, todays security authorizations should be claims based.

## Approaches

Unfortunately I haven't been able to figure out how to connect the dots
with the plethora of Azure authorization options.

### App Roles

It looks as though [Azure AD `AppRoles`][aad-app-roles] provide the coarse
grained RBAC that will allow our customer to integrate with their customer's
AD-based authorization models. Yet I see no tie into any fine grained permissions.
So it seems as either a dead end or a hook to another app-driven model
using the app role id.

### V2 App Roles

[Azure AD v2.0 endpoint][aad-v2] is touted as the future but all the\
limitations stated made this a non-starter.

### Azure AD B2C

[Azure AD B2C][aad-b2c] seem to provide the traditional OAuth2 scopes and
permissions but has separate costing and requires a [separate Azure AD Tenant][aad-b2c-tenant]
and seems to require AD federation to work with the rest of the AD Security
system. It does seem to be the sanctioned approach for using social
authentication accounts.

### Azure AD Connect & Azure AD B2B

[Azure AD Connect][aad-connect] and [Azure AD B2B][aad-b2b] seem to have
overlapping goals and I haven't figured out how either would provide the
mapping needed from the Federated partner's AD groups/claims to the App
Roles or other claims.

# What am looking to do

It may be best to just set up the fine grained security within the
application. However, having done it several times at enterprise scale,
I know it is not quick and easy. I had hoped there would be an AzMan-like
solution in Azure by now, but it appears the Azure has a very fractured
security solution.

My plan going in was to simply use nested AD Security groups for
fine-grained permissions and use the [Claims transformation][aad-transforms]
feature of the .NET OpenID Connect middleware to provide normalized claims
within the application. However I'm concerned about making the JWT token
size too large.

# A question of multitenancy

A word on multitenancy. Azure has documentation about multitenant SaaS applications,
but it seems to speak in terms of Azure tenants. Our customer need
multiple tenants but they don't need or want their clients to have to set
up Azure AD clients, etc. Does my client do so on their behalf to get Azure's
multitenancy support to work? Will the multitenancy support even work for
some of these azure security services such as Azure AD B2C? There seems
to be some indication that some do not.

# A question of scopes and resource permissions

I believe a traditional OAuth2 model would use scopes to limit access to
application resources. All that I've read so far in Azure documentation
has been about apps getting access to user resources. However I think it
works both ways and apps can specify users' access to application resources.
This was the model I was hoping to use but it doesn't seem to be
supported in anything but Azure AD B2C. What am I missing?

# Help

If you can provide any resources or guidance to help me I would greatly
appreciate it using the contact info at the top of this article. Thanks!

[aad-adal]: https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-authentication-libraries
[aad-app-roles]: https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/app-roles
[aad-b2b]: https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b
[aad-b2c]: https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-overview
[aad-b2c-tenant]: https://docs.microsoft.com/en-us/azure/active-directory-b2c/active-directory-b2c-get-started
[aad-connect]: https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect
[aad-graph]: https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-graph-api
[aad-transforms]: https://docs.microsoft.com/en-us/azure/architecture/multitenant-identity/claims#claims-transformations
[aad-v2]: https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-appmodel-v2-overview
[msft-graph]: https://developer.microsoft.com/en-us/graph/docs/concepts/overview
[win-azman]: https://msdn.microsoft.com/en-us/library/bb897401.aspx
