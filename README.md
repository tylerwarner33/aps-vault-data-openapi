# aps-vault-data-openapi

## Automated API Client Generation

This repository includes an automated GitHub Actions workflow that generates API clients using [Microsoft Kiota](https://learn.microsoft.com/en-us/openapi/kiota/overview) whenever the OpenAPI specification (`VaultDataApi.yml`) is updated via a pull request.

### How It Works

1. **Trigger**: The workflow automatically runs when a pull request modifies `VaultDataApi.yml`
2. **Generation**: Uses Microsoft Kiota to generate API clients for multiple languages (currently C#)
3. **Artifact**: The generated clients are uploaded as a workflow artifact for review
4. **PR Comment**: A summary comment is added to the PR with details about the generated clients

### Generated Clients

The workflow generates clients for:
- **C#**: Located in `Generated/ApiClients/CSharp/`
  - Class name: `VaultApiClient`
  - Namespace: `VaultDataApi`

### Reviewing Generated Client Changes

When you create a PR that updates `VaultDataApi.yml`:

1. Wait for the "Generate API Clients with Kiota" workflow to complete
2. Check the PR comment for a summary of the generated clients
3. Download the client artifacts from the workflow run
4. Compare with any existing client implementations to understand the API changes
5. Review the generated client code to validate the changes match your expectations

This allows you to see exactly how changes to the OpenAPI spec affect the generated client code before merging.

## What is OpenAPI?

From the [OpenAPI Specification](https://github.com/OAI/OpenAPI-Specification):

> The OpenAPI Specification (OAS) defines a standard, programming language-agnostic interface description for HTTP APIs, which allows both humans and computers to discover and understand the capabilities of a service without requiring access to source code, additional documentation, or inspection of network traffic. When properly defined via OpenAPI, a consumer can understand and interact with the remote service with a minimal amount of implementation logic. Similar to what interface descriptions have done for lower-level programming, the OpenAPI Specification removes guesswork in calling a service.

## Resources

### Documentation

- [Vault Data API](https://aps.autodesk.com/en/docs/vaultdataapi/v2/reference/http/)

### Repositories

- Autodesk: [aps-sdk-openapi](https://github.com/autodesk-platform-services/aps-sdk-openapi)

### Blogs

- [Become an early adopter of the new Vault Data APIs](https://aps.autodesk.com/blog/become-early-adopter-new-vault-data-apis)
- [OpenAPI Specs Are Here](https://aps.autodesk.com/blog/openapi-specs-are-here)
- [Using APS OpenAPI Specs with Postman](https://aps.autodesk.com/blog/using-aps-openapi-specs-postman)
- [Generate Your Own APS Clients Using OpenAPI and Microsoft Kiota](https://aps.autodesk.com/blog/generate-your-own-aps-clients-using-openapi-and-microsoft-kiota)

### Recordings

- Autodesk University: [OpenAPI Unleashed: Powering AI Agents and Low-Code Automations with Autodesk Platform Services.](https://www.autodesk.com/autodesk-university/class/OpenAPI-Unleashed-Powering-AI-Agents-and-Low-Code-Automations-with-Autodesk-Platform-Services-2025)
