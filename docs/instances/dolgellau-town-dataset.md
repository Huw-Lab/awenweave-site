!!! info "Welsh translation pending"
    A Welsh-language version of this page is being prepared during
    the Tuesday tutor session (week of 2026-05-19). Until then, the
    Welsh-language version of the site shows the placeholder.

# Dolgellau Town Dataset

Awen Weave's first public instance. A place-hosted, community-operated
record of the town of Dolgellau — its buildings, histories, and the
people and decisions woven around them.

## What the dataset holds

The dataset is a structured record of Dolgellau as a built place. It
holds:

**Buildings** — every recorded building in the town: address, footprint,
listed-status where applicable, historic register entries, energy
performance certificates, ownership history, planning history. Held as
*claims with provenance* rather than as opaque values; every fact carries
the source it came from and the date it was made.

**Histories** — the stories told about each building, drawn from local
archive, oral tradition, photography collections, and contemporary
curatorial work. Histories are themselves recorded entities with their
own provenance.

**People and decisions** — the people who made the decisions about each
building, where those decisions are recorded. Records of curatorial
judgements about contested claims. Field-verification co-signatures
where two curators stood in the same street and confirmed a correction
together.

**Sources** — every cited reference is itself a first-class record:
where it was published, what it covered, who maintains it, its
visibility rules, its retirement conditions. There is no "trust me"
anywhere; every layer of trust is examined.

## How it works

The dataset runs on Awen Weave — the pattern that names its parts in
Welsh: [Llys / Craidd / IDRIS / Prawf / Craffter](../about/framework.md).
Curators interact through the framework's CLIs:

- `craidd-init` — initialise and refresh the canonical store
- `craidd-propose` — submit new claims and entities to the proposal queue
- `lleolydd-cache` — manage cached snapshots of OGL source data (HMLR Price
  Paid, OS Open Data, EPC register)

Field correction — checking that a recorded address matches the building
actually standing at that point — uses
[Lleolydd](../about/framework.md), a curator iPad tool for in-place
UPRN/TOID verification.

## Where it lives

The dataset is physically hosted on a Raspberry Pi at
[Arloesi Dolgellau](https://arloesidolgellau.com/) — the Community
Interest Company that operates the instance — in the town of Dolgellau
itself. The relationship between the data and the place it describes is
not abstract. Trust is grounded in proximity.

This is not metaphor. There is a Raspberry Pi 5 in Y Stiwdio on
Glyndwr Street, Dolgellau, holding the canonical DuckDB store and the
Prawf log. When the dataset records something about a building on
Bridge Street, the record lives 200 metres from the building it
describes.

## Who owns the dataset

The content is owned by the operating community — Arloesi Dolgellau
CIC. The framework that the dataset runs on (Awen Weave) is licensed by
[Awen Weave Limited](../commercial/index.md).

The boundary is structural:

| Layer | Owner | License |
|-------|-------|---------|
| Content (the buildings, histories, sources) | Arloesi Dolgellau CIC | Open Government Licence (OGL) |
| Framework (the code that holds the content) | Awen Weave Limited | AGPLv3 + commercial dual |

The community owns what is woven. The framework owns the loom.

## Status

The dataset is operational. As of May 2026:

- **Schema:** v0.1 — claims-with-provenance with hash-chained Prawf log
- **Coverage:** Dolgellau LL40 postcode area (~3,200 UPRNs); expanding
- **Curators:** active proposal review and field-verification workflow
- **Source seeds:** HMLR Price Paid, HMLR OCOD, EPC register, OS Open
  Data, Estate Agent Listings (via Building Research Agent)
- **Operational finding:** 95.54% of Gwynedd UPRN→building matches are
  contested-prox under polygon-fidelity testing — vindication of the
  curator discipline that underpins the dataset

## Getting involved

If you would like to become a curator of the Dolgellau Town Dataset,
the conversation is with [Arloesi Dolgellau](https://arloesidolgellau.com/).
Curatorship is granted by the operating community after a conversation
about commitment, capability, and trust — see [For Curators](../curators/index.md).

If you would like to contribute knowledge about a Dolgellau building
without becoming a curator, the proposal route is open: write to
Arloesi Dolgellau with what you know and where it came from. The
curators will treat your contribution as a proposed claim, just as
they treat anything else entering the canonical record.

## Beyond Dolgellau

The Dolgellau Town Dataset is the first instance of Awen Weave; others
will follow in other places and other domains. The pattern is
[available for any community](../developers/index.md) that wants to
weave together what it knows about itself. The framework is
[licensable for commercial use](../commercial/index.md) where
proprietary terms are needed.

The next instance might be in your town. Or it might be a construction
contractor managing the golden thread for a Tier 1 project. Or a
third-sector charity stewarding its knowledge across decades. The
pattern is the same; the application is wherever the work is.
