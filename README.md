# Example Nestjs App with Tilt

Requirements: [Tilt](https://tilt.dev/)

To start the app run:

```
tilt up
```

Tilt will assemble an image, deploy the app, and live update using Docker Compose.

View the app at http://localhost:3000/

When you make a change to [app.service.ts](src/app.service.ts), Tilt will sync the file to the container and restart the app.

# Endpoints

## Hello World

```sh
curl http://localhost:3000
```
