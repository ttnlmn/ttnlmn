### Hi, I'm ttnlmn 👋

I build open-source deployment tooling at [Sentiens](https://www.sentiens.fr) ([LinkedIn](https://www.linkedin.com/company/sntns)).

#### Projects

| Project | What it does |
|---|---|
| **[nemo](https://github.com/sntns/nemo)** | Ship applications made of containers to any Docker host, as versioned [CNAB](https://cnab.io) bundles: Compose on one machine, Swarm on many, even on a site with no network. |
| **[terraform-provider-nemo](https://github.com/sntns/terraform-provider-nemo)** | Deploy nemo stacks from Terraform or OpenTofu: `sntns/nemo` on the [Terraform](https://registry.terraform.io/providers/sntns/nemo) and [OpenTofu](https://search.opentofu.org/provider/sntns/nemo) registries. |
| **[terraform-provider-swarm](https://github.com/sntns/terraform-provider-swarm)** | Init or adopt a Docker Swarm cluster from Terraform or OpenTofu, and keep its nodes' roles, labels and availability: `sntns/swarm` on the [Terraform Registry](https://registry.terraform.io/providers/sntns/swarm). |

```hcl
resource "nemo_stack" "shop" {
  name   = "shop"
  remote = "docker://registry.example.com/shop/{{ .Component }}:{{ .Version }}"
  target = { orchestrator = "swarm", host = "ssh://deploy@prod-1.example.com" }
  installations = [
    { name = "api", version = "1.4.0" },
    { name = "frontend", version = "1.4.0" },
  ]
}
```

#### Mostly working with

Go · Docker · Docker Swarm · Compose · Terraform · OpenTofu · CNAB · OCI registries
