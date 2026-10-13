# Cloud Security — Attack Architecture Map

A single-page, self-contained reference site mapping cloud attack paths across **AWS, Azure, and GCP** — identity abuse, metadata-service pivots, container/Kubernetes escapes, serverless exploitation, CI/CD supply-chain compromise, and storage exposure — paired with the detection signal and misconfiguration checks that catch each one.

Built the same way as an AD attack-path map, but for the cloud control plane: no backend, no build step, no dependencies. Open `index.html` and it works.

Website Link : https://balabm7.github.io/Cloud-Security-/

## View it locally

```bash
git clone https://github.com/<your-username>/cloud-attack-architecture-map.git
cd cloud-attack-architecture-map
open index.html   # or just double-click it
```

## Host it on GitHub Pages

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under **Source**, pick the `main` branch and `/ (root)` folder.
4. Save — your map is live at `https://<your-username>.github.io/cloud-attack-architecture-map/`.

## What's covered

- **Identity & IAM abuse** — AWS `PassRole` chains, Azure Managed Identity token theft, GCP `actAs`/service-account impersonation
- **Attack flow chains** — SSRF → IMDS → IAM pivot, leaked CI secret → supply-chain compromise, container escape → cluster pivot, and more
- **Containers & Kubernetes** — privileged pod escape, exposed kubelet, RBAC sprawl
- **Serverless** — over-privileged execution roles, event-source injection, dependency/layer poisoning
- **CI/CD & supply chain** — OIDC trust misconfig, secrets in pipeline logs, dependency confusion
- **Storage & data exposure** — public buckets, anonymous blob/GCS access, exposed databases
- **Detection** — log source → what it catches → key event, per provider (CloudTrail, Entra sign-in logs, GCP Audit Logs, K8s audit logs, CI/CD run logs)
- **OPSEC noise levels** — which techniques are quiet vs. which trip alerts immediately
- **CVE / advisory watch** — a template section to keep current with new platform advisories
- **Misconfiguration checklist** — the findings that show up in nearly every cloud assessment

## Keeping it current

The **CVE Watch** section (`#cves`) ships as a template — swap in real advisories as they land so the page doesn't go stale. Everything else is plain HTML/CSS in `index.html`; edit directly, no build tooling required.




