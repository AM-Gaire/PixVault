# PixVault 🖼️
### Cloud-Native Image Sharing Platform

Built and deployed on Microsoft Azure for COM682 Cloud Native Development.

## Azure Resources Used
- **Azure App Service** — WordPress web application hosting
- **Azure Blob Storage** — Binary image file storage
- **Azure MySQL Flexible Server** — Relational database for metadata
- **Azure Logic Apps** — REST API orchestration (CRUD operations)
- **Azure Application Insights** — Monitoring and telemetry

## REST API Endpoints (Logic Apps)
| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | /wp-json/wp/v2/media | List all images |
| GET | /wp-json/wp/v2/media/{id} | Get single image |
| POST | /wp-json/wp/v2/media | Upload new image |
| PUT | /wp-json/wp/v2/media/{id} | Update image |
| DELETE | /wp-json/wp/v2/media/{id} | Delete image |

## Live URL
https://amrit-edaedkguctc9gvbf.switzerlandnorth-01.azurewebsites.net

## Student
- **Name:** Amrit Gaire
- **Student Number:** B00969184
- **Module:** COM682 – Cloud Native Development (QAHE)
