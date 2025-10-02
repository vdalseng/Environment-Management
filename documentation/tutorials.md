# Tutorials
### Kubernetes and Kind
Follow the tutorial in the file [Kubernetes-kind.md](Kubernetes-kind.md) to set up a local Kubernetes cluster using Kind (Kubernetes IN Docker).

Extra resources on Kubernetes and Kind:

Spinning up development Kubernetes clusters easily with Kind: [https://www.youtube.com/watch?v=WfztIkIcGOs](https://www.youtube.com/watch?v=WfztIkIcGOs).

Official Kind documentation: [https://kind.sigs.k8s.io/](https://kind.sigs.k8s.io/).


### Application Packaging with Podman or Docker
To deploy an application to a Kubernetes Cluster, you first need to package it into a container image. You can use either Podman or Docker for this purpose. Below are the steps to build a container image using both tools.

#### Using Podman
Write a Dockerfile in your project directory. Here is a simple example for a Node.js application:

```Dockerfile
FROM node:14
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "app.js"]
```

Build the container image using Podman:
```bash
podman build -t my-app:latest .
```

Run the container locally to test it:
```bash
podman run -p 3000:3000 my-app:latest
```

push the image to a container registry (e.g., Docker Hub, Podman Hub):
```bash
podman tag my-app:latest <your-registry-username>/my-app:latest
podman push <your-registry-username>/my-app:latest
```

[]()