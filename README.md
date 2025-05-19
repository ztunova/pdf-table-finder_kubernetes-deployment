# PDF Table Finder Deployment
This directory contains Kubernetes configuration files for deploying the PDF Table Finder application on a CERIT Kubernetes cluster.

## Related Repositories
- PDF Table Finder front-end: https://github.com/ztunova/pdf-table-finder_FE
- PDF Table Finder back-end: https://github.com/ztunova/pdf-table-finder_BE

## Deployment
The application is deployed on the CERIT Kubernetes cluster. To get access to the CERIT infrastructure and configure local environment, follow the instructions provided at the following URLs:
- access to CERIT infrastructure: https://docs.cerit.io/en/docs/platform/access
- access to Harbor Docer registry: https://docs.cerit.io/en/docs/docker/harbor
- install and configure `kubectl`: https://docs.cerit.io/en/docs/kubernetes/kubectl

After completing the setup, proceed with building the Docker image, pushing it to the container registry, and applying the deployment configuration.
1) `docker build  . -t cerit.io/{user_name}/{image_name}:{version}`
2) `docker push cerit.io/{user_name}/{image_name}:{version}`
3) `kubectl apply -f {filename} -n {namespace}`

## Structure
```
/
├── be/                  # Configuration for back-end
│   ├── deployment.yaml
|   ├── service.yaml
|   └── ingress.yaml
└── fe/                  # Configuration for front-end
│   ├── deployment.yaml
|   ├── service.yaml
|   └── ingress.yaml
```