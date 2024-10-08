# Data Source: mongodbatlas_encryption_at_rest_private_endpoints

`mongodbatlas_encryption_at_rest_private_endpoints` describes private endpoints of a particular cloud provider used for encryption at rest using customer-managed keys.

## Example Usages

```terraform
data "mongodbatlas_encryption_at_rest_private_endpoints" "plural" {
  project_id     = var.atlas_project_id
  cloud_provider = "AZURE"
}

output "number_of_endpoints" {
  value = length(data.mongodbatlas_encryption_at_rest_private_endpoints.plural.results)
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `cloud_provider` (String) Human-readable label that identifies the cloud provider for the private endpoints to return.
- `project_id` (String) Unique 24-hexadecimal digit string that identifies your project.

### Read-Only

- `results` (Attributes List) List of returned documents that MongoDB Cloud providers when completing this request. (see [below for nested schema](#nestedatt--results))

<a id="nestedatt--results"></a>
### Nested Schema for `results`

Read-Only:

- `cloud_provider` (String) Label that identifies the cloud provider of the private endpoint.
- `error_message` (String) Error message for failures associated with the Encryption At Rest private endpoint.
- `id` (String) Unique 24-hexadecimal digit string that identifies the Private Endpoint Service.
- `private_endpoint_connection_name` (String) Connection name of the Azure Private Endpoint.
- `project_id` (String) Unique 24-hexadecimal digit string that identifies your project.
- `region_name` (String) Cloud provider region in which the Encryption At Rest private endpoint is located.
- `status` (String) State of the Encryption At Rest private endpoint.

For more information see: 
- [MongoDB Atlas API - Private Endpoint for Encryption at Rest Using Customer Key Management](https://www.mongodb.com/docs/atlas/reference/api-resources-spec/v2/#tag/Encryption-at-Rest-using-Customer-Key-Management/operation/getEncryptionAtRestPrivateEndpointsForCloudProvider) Documentation.
- [Manage Customer Keys with Azure Key Vault Over Private Endpoints](https://www.mongodb.com/docs/atlas/security/azure-kms-over-private-endpoint/).
