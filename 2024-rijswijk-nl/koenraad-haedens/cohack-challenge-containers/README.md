# CoHack Challenge : Containers

**Speaker(s):** Koenraad Haedens — session on the [European MCT Summit 2024, Rijswijk](https://european-mct-summit-2024.sessionize.com/) agenda.

## Abstract

This is a 2h30 challenge and will cover the basics of containers and container runtimes, they get familiar with the components of the application they will use throughout this hack.

the challenge has the following steps:

Build the API image in provisioned devops jump vm .
Build the WEB image in provisioned devops jump vm .
push your images to your ACR (Azure Container Registry) (will be provisioned in speakers subscription)
Deploy the API image as Azure Container Instance in Azure, make sure that the API can connect to the database
Deploy the WEB frontend as Azure Container Instance that will connect to the API
