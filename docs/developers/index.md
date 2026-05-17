!!! info "Welsh translation pending"
    A Welsh-language version of this page is being prepared during
    the Tuesday tutor session (week of 2026-05-19). Until then, the
    Welsh-language version of the site shows the placeholder.

# For developers

Awen Weave is distributed as a Python package on PyPI. Anyone can
install it and use it; community deployments are open under AGPLv3,
and commercial deployments are licensed separately.

## Install

```bash
pip install awen-weave
```

Requires Python 3.10 or newer. The package installs the framework CLIs
(`craidd-init`, `craidd-propose`, `lleolydd-cache`) as console entry
points; importable modules cover schema validation, predicates,
storage, and the OGL cache layer.

## Repository

The source code lives at [github.com/Huw-Lab/awen-weave](https://github.com/Huw-Lab/awen-weave).
The repository is the authoritative source; PyPI carries the published
releases.

## What's in the framework

The framework provides the five-part architecture documented in
[The framework](../about/framework.md): Llys, Craidd, IDRIS, Prawf,
Craffter. In code terms:

- `craidd/` — schema, validators, predicates, canonical storage
- `cli/` — `craidd-init`, `craidd-propose`, `lleolydd-cache` entry points
- `lleolydd/` — Open-Government-Licence cache layer (HMLR, OS, EPC sources)
- `client/` — `craidd_client.py` library for programmatic instance work

Each layer is designed so that an instance can use it as-is, extend it
where needed, and replace it where genuinely necessary — without
compromising the framework's constitutional principles
([contracts, judgement, learning](../about/index.md#the-principles)).

## What's not in the framework — and why

Awen Weave deliberately ships *the pattern*, not *the data*. The
framework holds nothing about any particular place, organisation, or
domain. Specifically, the framework does NOT include:

- **Place-specific seed data** — buildings, sources, agent registries
  for any particular instance. These belong in the instance repository.
- **Place-specific configuration** — agent manifests, geographic bounds,
  postcode prefixes. These belong in the instance's `config/` directory.
- **Place-specific identity** — submitter IDs, recorder IDs, contact
  emails. The framework leaves these for instances to set.

If you see place-specific data in the framework, that's a bug — please
file an issue.

## Versioning

Awen Weave follows semantic versioning. The current series is v0.x —
breaking changes may land between minor versions until v1.0.0
stabilises the API for commercial-customer dependency contracts.

Pin specific versions in your instance's `requirements.txt`:

```
awen-weave==0.1.0
```

## Setting up an instance

A new instance is its own repository, separate from the framework, that
consumes `awen-weave` from PyPI and holds the place-specific content
plus configuration. The pattern is documented in
`design/migration-2026-05.md` in the framework repository; the live
reference instance is the [Dolgellau Town Dataset](../instances/dolgellau-town-dataset.md).

A minimal instance contains:
- `requirements.txt` pinning a specific `awen-weave` version
- `config/` for instance-specific configuration (agents, bounds, identity)
- `seed/` for instance-specific content (buildings, sources)
- A `STATUS.md` describing the instance's operational state

The framework CLIs (`craidd-init`, etc.) operate against the instance's
configured store; no instance-specific code is needed for typical
operations.

## License

Awen Weave is dual-licensed:

**AGPLv3 — for community and open deployments.** If you fork, modify,
or deploy Awen Weave in a way that touches a network service, the AGPL
requires that you publish your modifications under the same terms. This
is the standard open-source path; for instances like the
[Dolgellau Town Dataset](../instances/dolgellau-town-dataset.md) operated
by a community, this is the natural license.

**Commercial license — for proprietary deployments.** If you need to
deploy Awen Weave in a way that doesn't fit AGPL — modifications stay
private, no copyleft on derivative work, support and indemnity
clauses — a commercial license is available from
[Awen Weave Limited](../commercial/index.md). Contact
huw@awenweave.com.

The framework code is licensed by [Awen Weave Limited](../commercial/index.md);
the framework writing on this site (and in the repository's `design/`
folder) is licensed CC-BY-SA 4.0; the framework name and trademark
("AWEN WEAVE") are owned by Awen Weave Limited.

## Contributing

External code contributions will require a Contributor License Agreement
(CLA) once the template is finalised — expected mid-2026. In the
interim:

- **Issues** for bug reports, feature requests, and documentation
  suggestions are welcome at the [repository](https://github.com/Huw-Lab/awen-weave/issues).
- **Pull requests** will be acknowledged but held pending the CLA
  process.
- **Internal contributions** (Awen Weave Limited maintainers) follow
  the conventions in `CONTRIBUTING.md` and STATUS.md.

## Getting started

The simplest exploration path:

```bash
python -m venv .venv
source .venv/bin/activate
pip install awen-weave
craidd-init --help
craidd-propose --help
lleolydd-cache --help
```

Each CLI's `--help` describes its surface. The framework design notes
in the repository's `design/` folder give the conceptual context for
each part of the architecture.

For a working instance to read alongside, see
[github.com/arloesidolgellau/town-dataset](https://github.com/arloesidolgellau/town-dataset)
(public release pending the completion of the framework migration arc).
