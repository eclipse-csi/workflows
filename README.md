# Workflows
Collection of reusable workflows and actions.

## upload-sbom

A composite action for authenticated SBOM upload to the Eclipse Foundation
DependencyTrack instance.

### Prerequisite

Before using this action, please request upload permission for your GitHub
repository and the `product-name` you want to use from the [Eclipse Foundation
Security Team](https://www.eclipse.org/security/).

> [!IMPORTANT]
> Upload permission is granted for a `product-name`. If you want to change
> `product-name`, you must re-request permission.

### Usage

#### Permission
The upload-sbom action uses an OIDC token to authenticate the upload. To mint
the token, the following permission block must be set in the calling action.

```yaml
permissions:
  id-token: write
```

#### Example

```yaml
- uses: eclipse-csi/workflows/upload-sbom@<pin to sha!>
  with:
    sbom-file: 'path/to/openvsx-server-sbom.json'
    product-name: 'openvsx-server'
    product-version: 'v1.0.0'
```

#### Example (staging)

```yaml
- uses: eclipse-csi/workflows/upload-sbom@<pin to sha!>
  with:
    sbom-file: 'path/to/openvsx-server-sbom.json'
    product-name: 'openvsx-server'
    product-version: 'v1.0.0'
    staging: true
```
