# targetgroup_binding_helmchart

A Helm chart to organize and manage AWS Target Group Bindings, designed for deployment and continuous delivery via ArgoCD.

## Purpose

This Helm chart simplifies the organization and deployment of AWS Target Group Bindings, making it easy to manage these resources declaratively and deploy them through GitOps workflows using ArgoCD.

## Prerequisites

- [ArgoCD](https://argo-cd.readthedocs.io/en/stable/) for continuous deployment and GitOps management.
- A Kubernetes cluster with necessary permissions to manage AWS TargetGroupBinding resources.
- Helm 3.x or newer.

## Installation

Add this repository to your Helm setup:

```sh
helm repo add <repo-name> <repository-url>
helm repo update
```

Deploy the chart using ArgoCD or Helm:

### Using ArgoCD

1. Create an Application in ArgoCD pointing to this chart repository.
2. Configure your `values.yaml` as required.
3. Sync the application to deploy.

### Using Helm CLI

```sh
helm install my-targetgroup-binding <repo-name>/targetgroup_binding_helmchart -f values.yaml
```

## Configuration

Customize your deployment by editing the `values.yaml` file. Example configuration:

```yaml
aws:
  targetGroupBindings:
    - name: example-binding
      targetGroupARN: arn:aws:elasticloadbalancing:...
      serviceRef:
        name: my-service
        port: 80
```

> **Note:** Replace placeholder values with your actual AWS resources and Kubernetes service references.

## Features

- Declarative target group binding management for AWS in Kubernetes.
- GitOps-friendly: easily managed and updated via ArgoCD.
- Modular and reusable chart structure.

## Limitations

- Requires ArgoCD for GitOps workflows (for continuous deployment).
- Assumes you have appropriate IAM permissions set up in your cluster for AWS operations.
- The chart is focused on AWS TargetGroupBinding resources.

## Contributing

Contributions are welcome! Please open issues or pull requests for bug fixes, features, or suggestions.

## License

MIT License

---

_For questions or support, please open an issue in this repository._
