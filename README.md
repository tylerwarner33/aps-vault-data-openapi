# aps-vault-data-openapi

This repo is used for updating the Autodesk Vault Data API OpenAPI specification since it is not currently included in the [aps-sdk-openapi](https://github.com/autodesk-platform-services/aps-sdk-openapi) repo. The versioning from the [Vault Data API OpenAPI specification endpoint](https://aps.autodesk.com/en/docs/vaultdataapi/v2/reference/http/getapispec-GET/) will remain to know if it is synced. A text comparison can be used to know what has been updated.

## Automated API Client Generation

This repository includes an automated GitHub Actions workflow that generates API clients using [Microsoft Kiota](https://learn.microsoft.com/en-us/openapi/kiota/overview) whenever the OpenAPI specification (`VaultDataApi.yml`) is updated via a pull request.

### How It Works

1. **Trigger**: The workflow automatically runs when a pull request modifies `VaultDataApi.yml`.
2. **Generation**: Uses Microsoft Kiota to generate API clients for specified languages (currently C#).
3. **Artifact**: The generated clients are uploaded as a workflow artifact for comparison & review.
4. **Comment**: A summary comment is added to the PR with details about the generated clients.
4. **Merge**: Once the PR is approved & merged, another workflow will run to generate the API clients & commit the changes.

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
