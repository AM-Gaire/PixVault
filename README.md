# PixVault 🖼️

### Cloud-Native Image Sharing Platform

PixVault is a cloud-native image sharing platform built and deployed entirely on Microsoft Azure. It was developed for the COM682 Cloud Native Development module, and demonstrates a serverless, API-driven architecture for storing, retrieving, and managing images at scale without managing traditional servers.

## Features

- Upload, list, retrieve, update, and delete images through a REST API
- Image binaries stored in Azure Blob Storage, decoupled from metadata
- Relational metadata storage using Azure MySQL Flexible Server
- API orchestration handled by Azure Logic Apps (no custom backend server required)
- Application performance and usage monitored via Azure Application Insights

## Architecture

```
Client
  |
  v
Azure App Service (WordPress front end)
  |
  v
Azure Logic Apps  --->  REST API orchestration (CRUD)
  |                            |
  v                            v
Azure Blob Storage      Azure MySQL Flexible Server
(image files)           (image metadata)
  |
  v
Azure Application Insights (monitoring & telemetry)
```

## Tech Stack

| Layer | Azure Service | Purpose |
|---|---|---|
| Hosting | Azure App Service | WordPress web application hosting |
| Storage | Azure Blob Storage | Binary image file storage |
| Database | Azure MySQL Flexible Server | Relational database for image metadata |
| API | Azure Logic Apps | REST API orchestration (CRUD operations) |
| Monitoring | Azure Application Insights | Performance monitoring and telemetry |

## REST API Reference

| Method | Endpoint | Description |
|---|---|---|
| GET | `/wp-json/wp/v2/media` | List all images |
| GET | `/wp-json/wp/v2/media/{id}` | Get a single image |
| POST | `/wp-json/wp/v2/media` | Upload a new image |
| PUT | `/wp-json/wp/v2/media/{id}` | Update an existing image |
| DELETE | `/wp-json/wp/v2/media/{id}` | Delete an image |

## Deployment Overview

The platform is provisioned entirely on Azure:

1. An App Service instance hosts the WordPress-based front end used to browse and manage images.
2. Blob Storage holds the raw image files, keeping large binary data out of the database.
3. MySQL Flexible Server stores structured metadata (titles, IDs, timestamps) for each image.
4. Logic Apps expose the REST endpoints above and orchestrate CRUD operations between the front end, storage, and database.
5. Application Insights is wired in for monitoring, logging, and telemetry across the stack.

## Live Demo

[PixVault on Azure](https://amrit-edaedkguctc9gvbf.switzerlandnorth-01.azurewebsites.net)

## Project Context

This project was built as part of COM682 - Cloud Native Development (QAHE).

- Author: Amrit Gaire
- Module: COM682 - Cloud Native Development

## Author

Amrit Gaire
GitHub: [@AM-Gaire](https://github.com/AM-Gaire)
