# Azure AD Questions for Microsoft

## Background

Our requirement is:

- Multitenant SaaS application supporting Azure AD B2B and Azure Connect
- Fine Grain Role Based Access Control (RBAC)
- Host-only roles
- Provision of Fine-Grained RBAC permissions to client API
- Must work with application software:
  - Angular 4 served by NodeJS via iisnode in a Web Node
    - Client uses ADAL for authentication
  - Web API 2 backend in a Web Node

## Current Approach

### Azure App Roles

It appears that Azure App Roles will provide adequate Coarse Grained
RBAC to meet our needs. However we see to things lacking

- Mapping to App Roles to Fine-Grained RBAC permissions
- Support for roles that are not exposed to client tenants for global
  application administrators.

## Questions

1. Is there a facility for Fine-Grained RBAC permissions that integrates
   with Azure AD B2B and Azure Connect?
1. Is there a way to have App Roles that do not get exposed to Azure AD
   B2B tenants?
1. If there is not a way to have host-only App Roles, can both App Roles
   and Azure security groups be used as roles together?
1. Do you have any examples that use Web API 2 vs. .NET Core?

## Appendix: Supporting Links

- [ADAL][aad-adal]
- [Windows Authorization Manager (AzMan)][win-azman]
- [Claims transformation][aad-transforms]
- Azure AD [AppRoles][aad-app-roles]
- Azure AD [v2.0 endpoint][aad-v2]
- Azure AD [B2B][aad-b2b]
- Azure AD [B2C][aad-b2c]
- Azure AD [Connect][aad-connect]
- Azure AD [Graph API][aad-graph]
- Microsoft [Graph API][msft-graph]

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