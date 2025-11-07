
# 🧩Kustomize Multi-Environment Example

This Project demonstrates how to use Kustomize to manage multiple Kubernetes Environments - Development, Staging, and Production using a common base Configuration.

With this setup you can maintain a single source of truth for your Kubernetes resources while applying environment-specific customizations such as unique nodePort values for each environment.

## How It Works
Kustomize allows you to deine a **base configuration** once and create multiple **overlays** that modify only what's needed.  
In this project:  
* The **base** defines the common deployment and service specs.
* Each **overlay (dev/staging/production)** references the base and applies a patch to update only the nodePort field.  
This keeps your configuration **DRY** (Don't Repeat Yourself), clean and easy to maintain.
##  Apply to a Cluster

Deploy the configuration directly to your Kubernetes Cluster.
```bash
  kubectl apply -k ./dev
  kubectl apply -k ./staging
  kubecto apply -k ./production
```
**Or**  
To apply for all the environment at a time.
```bash
    kubectl apply -k .
```


## ✅Benefits

* **Reusable Base** - Define common configurations once.
* **Environment-Specific Overrides** - Customize only what's needed per environment.
* **Simplified Management** - Easily maintain and promote changes between environments. 
* **No YAML Duplication** - Keeps manifests clean and DRY.

