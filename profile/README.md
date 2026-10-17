<p align="center">
  <a href="https://lembos.dev">
    <img src="https://lembos.dev/logo.svg" alt="Lembos" width="96" height="96">
  </a>
</p>

<h1 align="center">Lembos</h1>

<p align="center">
  <strong>The control plane for how software is deployed, configured and governed.</strong><br>
  An open-source internal developer platform built on versioned building blocks.
</p>

<p align="center">
  <a href="https://lembos.dev">Website</a> ·
  <a href="https://lembos.dev/docs">Docs</a> ·
  <a href="https://lembos.dev/docs/quickstart">Quickstart</a> ·
  <a href="https://lembos.dev/docs/install">Install</a>
</p>

<p align="center">
  <sub>Latest release <strong>0.0.1</strong> — an early, pre-1.0 release; expect changes between versions.</sub>
</p>

---

Most engineering organisations answer three questions with three different systems that disagree with
each other: *what software do we have*, *what is running where*, and *was it allowed to get there*.
Lembos answers all three in one place.

It records what **should** be running, observes what **is**, and closes the gap. Teams get golden paths
they can use on their own; platform engineers change those paths without a migration across every team
at once; and anyone can ask what happened, months later, and get an exact answer.

Lembos is not just a developer portal, and not only a service catalog. A portal is how people reach it,
and a catalog is part of what it knows — neither is the thing itself.

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://lembos.dev/portal/releases-dark.png">
    <img src="https://lembos.dev/portal/releases-light.png" alt="A release in the Lembos Portal that went from the sandbox into production, deploying to the eu-west slot first and eu-north second." width="860">
  </picture>
</p>

## What it does

- **A catalog of your software.** Business domains, systems, components, APIs and resources, and how
  they depend on one another. API contracts keep their history, so a consumer still sees what it agreed
  to after the next version lands.
- **Golden paths as blueprints.** "How is this built and deployed" becomes a versioned recipe instead
  of tribal knowledge. A team declares its component against a blueprint and never has to learn the
  runtime underneath.
- **Everything versioned, nothing silently changed.** Blueprints, configuration, API contracts,
  policies and environments are all published as immutable versions. What a deployment pins cannot
  change under it, so replaying it a month later gives the same result.
- **Configuration that ships with the code.** Settings travel with the release, so promotion reviews
  them and a rollback takes them back. Overrides layer from common to environment to slot — a payment
  provider that differs per country is an override, not a fork. Secrets are referenced from your vault
  and never pass through the platform.
- **Environments that fit how you actually run.** One environment can be split into slots — per
  country for data residency, per region for latency. Review environments carry a lease and expire on
  their own instead of quietly running up a bill.
- **Releases you can trace.** A release freezes its contents and walks your environments in order.
  Production can take its regions one at a time with a person checking in between. *"Where was this
  version tested before production?"* always has an answer.
- **Drift you can see.** Every environment reports whether what is running matches what was asked
  for — after a half-finished rollout, a configuration published and never deployed, or a hand edit to
  a cluster.
- **Guardrails before, not audits after.** Who may act, what they own, and whether this particular
  change is allowed right now are three separate checks. "Production is limited to a few people while
  anyone may create a dev environment" is something you can actually express.
- **An audit trail by construction.** Every change is recorded, and every policy decision remembers the
  exact policy version it enforced, so a later edit cannot rewrite history.

## A look inside

<table>
  <tr>
    <td width="50%">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://lembos.dev/portal/component-dark.png">
        <img src="https://lembos.dev/portal/component-light.png" alt="A component's page: its blueprint, owner and system, and a graph of what it consumes and depends on.">
      </picture>
      <p align="center"><sub>Every component, what it is built from and what it depends on</sub></p>
    </td>
    <td width="50%">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://lembos.dev/portal/environment-prod-dark.png">
        <img src="https://lembos.dev/portal/environment-prod-light.png" alt="A production environment split into eu-north and eu-west slots, each healthy and matching what was asked for.">
      </picture>
      <p align="center"><sub>Environments split into slots, each reporting its own drift</sub></p>
    </td>
  </tr>
  <tr>
    <td width="50%">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://lembos.dev/portal/blueprint-versions-dark.png">
        <img src="https://lembos.dev/portal/blueprint-versions-light.png" alt="A blueprint's versions: one current, a draft, two deprecated and one withdrawn.">
      </picture>
      <p align="center"><sub>Golden paths as versioned blueprints, draft to withdrawn</sub></p>
    </td>
    <td width="50%">
      <picture>
        <source media="(prefers-color-scheme: dark)" srcset="https://lembos.dev/portal/policies-dark.png">
        <img src="https://lembos.dev/portal/policies-light.png" alt="The policies, each with what it governs, the version in force and when it is evaluated.">
      </picture>
      <p align="center"><sub>Guardrails checked before work is dispatched</sub></p>
    </td>
  </tr>
</table>

## Who it is for

| You are…                  | Lembos gives you…                                                                       |
|---------------------------|-----------------------------------------------------------------------------------------|
| **A product team**        | Self-service delivery on a golden path, without becoming an expert in the runtime       |
| **A platform team**       | One place to publish, evolve and retire the paths every team builds on                  |
| **Security & compliance** | Policy applied before work is dispatched, and a history you can reconstruct, not guess  |
| **Engineering leaders**   | A single, trustworthy view of what exists, where it runs and how it got there           |

## Run it yourself

There is no hosted Lembos. It runs in your own infrastructure and provisions into the clusters and
cloud accounts you already own. It is free and open source under the
[Apache 2.0 licence](https://github.com/lembosproj/deploy/blob/main/LICENSE).

- **Try it on your laptop** — the [quickstart](https://lembos.dev/docs/quickstart) puts a complete Lembos
  on a local k3s in about fifteen minutes.
- **Install it for your organisation** — the [install guide](https://lembos.dev/docs/install) covers the
  Helm chart, high availability, secrets and signing in with GitHub.
- **Learn how it thinks** — [concepts](https://lembos.dev/docs/concepts), then
  [using Lembos](https://lembos.dev/docs/use) for each part of the Portal.

## Repositories

| Repository                                                  | What it is                                                                   |
|-------------------------------------------------------------|------------------------------------------------------------------------------|
| [**deploy**](https://github.com/lembosproj/deploy)          | The Helm chart that installs Lembos into your Kubernetes cluster             |
| [**lembos.dev**](https://github.com/lembosproj/lembos.dev)  | The website and documentation — improvements to the docs are welcome here    |

## Get involved

Lembos is at 0.0.1 and moving quickly. Ideas, questions and contributions are welcome — read the
[contributing guide](https://github.com/lembosproj/deploy/blob/main/CONTRIBUTING.md) and the
[code of conduct](https://github.com/lembosproj/deploy/blob/main/CODE-OF-CONDUCT.md), or write to
[info@lembos.dev](mailto:info@lembos.dev).
