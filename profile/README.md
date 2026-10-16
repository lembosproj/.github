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
  <a href="https://github.com/lembosproj/deploy">Install</a>
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
    <img src="https://lembos.dev/portal/releases-light.png" alt="A release in the Lembos Portal moving from dev through test and staging, with production waiting on an ordered rollout across its eu-west and eu-north slots." width="860">
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

## Who it is for

| You are…                 | Lembos gives you…                                                                       |
|--------------------------|-----------------------------------------------------------------------------------------|
| **A product team**       | Self-service delivery on a golden path, without becoming an expert in the runtime       |
| **A platform team**      | One place to publish, evolve and retire the paths every team builds on                  |
| **Security & compliance**| Policy applied before work is dispatched, and a history you can reconstruct, not guess  |
| **Engineering leaders**  | A single, trustworthy view of what exists, where it runs and how it got there           |

## Run it yourself

There is no hosted Lembos. It runs in your own infrastructure and provisions into the clusters and
cloud accounts you already own, installed with the Helm chart in
[**deploy**](https://github.com/lembosproj/deploy). It is free and open source under the
[Apache 2.0 licence](https://github.com/lembosproj/deploy/blob/main/LICENSE).

## Get involved

Lembos is pre-1.0 and moving quickly. Ideas, questions and contributions are welcome — read the
[contributing guide](https://github.com/lembosproj/deploy/blob/main/CONTRIBUTING.md) and the
[code of conduct](https://github.com/lembosproj/deploy/blob/main/CODE-OF-CONDUCT.md), or write to
[info@lembos.dev](mailto:info@lembos.dev).
