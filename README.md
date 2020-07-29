# lens-helm3

Hologit lens for rendering Helm charts

## Extra namespace features

[https://github.com/helm/helm/issues/3553](Helm developers refuse to provide a way for the helm command to apply a namespace to generated objects).

This lens adds optional post-processing to do this for you, as this is the best location to do that in a Hologit-driven k8s GitOps pipeline since you want everything organized rendered namespaces before application to a cluster. It relies on a hardcoded list of namespacable kinds.

To set namespace on all namespace-able objects:

```toml
namespace = "my-namespace"
namespace_override = true
```

To only set namespace on namespace-able objects that have none defined already:

```toml
namespace = "my-namespace"
namespace_fill = true
```

## Roadmap

- [ ] Support [helmfile](https://github.com/roboll/helmfile) ?
