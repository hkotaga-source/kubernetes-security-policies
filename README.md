# Kubernetes Security Policies

A collection of practical Kubernetes security hardening manifests for SRE and Platform teams.

## What's included

- **NetworkPolicies** – default deny + allow specific traffic
- **Pod Security Standards** – restricted / baseline examples
- **Kyverno policies** – require labels, block privileged pods, image provenance
- **Resource Quotas & LimitRanges**
- **SecurityContext** best practices

## Quick Start

```bash
# Apply NetworkPolicies (start in a test namespace)
kubectl create namespace secure-demo
kubectl apply -f network-policies/ -n secure-demo

# Apply Kyverno (requires Kyverno installed)
kubectl apply -f kyverno/

# Apply Pod Security labels on a namespace
kubectl label namespace secure-demo pod-security.kubernetes.io/enforce=restricted
```

## Structure

```
network-policies/
kyverno/
pod-security/
resource-management/
```

## Why this matters

Most Kubernetes breaches happen because of overly permissive defaults. These policies help enforce least privilege and reduce blast radius.

Created for SRE/DevOps portfolio – https://github.com/hkotaga-source
