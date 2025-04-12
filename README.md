# RustDesk Server Kubernetes Deployment

This repository contains Kubernetes manifests for deploying RustDesk server using Argo CD.

## Components

The deployment consists of:

- **Deployment**: Manages the RustDesk server container
- **Service**: Exposes the RustDesk server ports
- **PersistentVolumeClaim** (optional): For data persistence
- **Kustomization**: For managing Kubernetes resources
- **Argo CD Application**: For GitOps-based deployment

## Directory Structure

```
.
├── README.md
└── k8s/
    ├── deployment.yaml
    ├── service.yaml
    ├── persistentvolumeclaim.yaml (optional)
    └── kustomization.yaml
└── argocd/
    └── application.yaml
```

## Ports

RustDesk server exposes several ports:

- 21115: HBBS TCP
- 21116: HBBS TCP and UDP
- 21117: HBBR TCP
- 21118: HBBR WebSocket
- 21119: HBBR WebSocket Secure

## Deployment Steps

1. Clone this repository to your GitHub account
2. Modify the Kubernetes manifests as needed
3. Update the `application.yaml` file with your GitHub repository URL
4. Apply the Argo CD application to your cluster:

```bash
kubectl apply -f argocd/application.yaml
```

5. Argo CD will synchronize and deploy the RustDesk server automatically

## Configuration

You may want to customize the deployment by:

- Changing the service type based on your infrastructure
- Adding persistent storage for data
- Setting resource limits and requests
- Using a specific image version instead of `latest`

## RustDesk Server Documentation

For more information about RustDesk server, visit the [official documentation](https://rustdesk.com/docs/en/).
