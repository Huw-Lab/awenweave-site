!!! info "Welsh translation pending"
    A Welsh-language version of this page is being prepared during
    the Tuesday tutor session (week of 2026-05-19). Until then, the
    Welsh-language version of the site shows the placeholder.

# The framework

Awen Weave is built from five named parts. Each has a specific job;
together they form the loom on which knowledge is woven.

## Llys — the interaction and decision layer

In Welsh, *Llys* means *court*. The Llys is where judgement happens
visibly. Curators interact with the system here. Decisions about what to
accept into the canonical record, what to reject, what to flag as
contested — all of these happen in the Llys.

The Llys principle: no decision is invisible. Every acceptance of a
claim, every rejection of a proposal, every override of an auto-derivation
is recorded with the curator's identity, the timestamp, the data state
at the moment of decision, and the reasoning. Audit reconstruction is
always possible.

## Craidd — the place-based trust core

In Welsh, *Craidd* means *core*. The Craidd is where canonical knowledge
lives. It is curated; it is provenance-bound; it has explicit
boundaries.

Three load-bearing decisions shape how Craidd holds knowledge:

**Records are claims, not values.** Every statement in Craidd is a claim
made by someone, citing something, at a particular time, with a particular
confidence. Multiple competing claims about the same subject coexist; a
canonical view is materialised from them, but it never silences the
competing claims. Contradictions are visible, not hidden.

**Sources are themselves entities.** A claim cites a source; the source
is itself a recorded entity in Craidd with its own provenance and
visibility rules. There is no opaque "trust me" anywhere; every layer of
trust is examined.

**The place is the trust anchor.** Each Craidd is hosted physically in
its place — the [Dolgellau Town Dataset](../instances/dolgellau-town-dataset.md)
lives on a Raspberry Pi at Arloesi Dolgellau, in Dolgellau. The
relationship between the data and the place it describes is not
abstract. The trust is grounded.

## IDRIS — reasoning and orchestration

*IDRIS* is named for Cadair Idris, the mountain south of Dolgellau.
The reasoning layer sits above Craidd and Prawf; it answers questions,
synthesises across sources, sequences operations. It is the layer that
brings together what Craidd holds and what Prawf records into useful
answers.

IDRIS is bounded: it reasons over what is in Craidd; it does not invent.
Where Craidd is silent, IDRIS is silent. Where Craidd is contested, IDRIS
surfaces the contradiction rather than choosing one side.

## Prawf — the obligation and proof layer

In Welsh, *Prawf* means *proof* or *test*. Prawf records the evidence of
process, not the correctness of outcome. Every decision the system makes
— every accepted claim, every superseded claim, every retired entity,
every co-signed field correction — generates a Prawf entry.

Prawf is append-only and hash-chained. Each entry includes the previous
entry's hash and its own hash, so the chain is tamper-evident.
Reconstruction of state at any past moment is possible by walking the
chain. The principle: *what was done is honoured by being recorded*.

## Craffter — pattern-level observation

In Welsh, *Craffter* means *perceptiveness* — the quality of one who is
observant. Craffter notices patterns across the data: trends, anomalies,
clusters of claims that fit together in unexpected ways. It is the
machine-learning layer where one exists.

Craffter has one inviolable boundary: it is advisory, not authoritative.
It never writes to Craidd; it never writes to Prawf. It surfaces
observations to humans, who decide whether the observation rises to a
claim worth recording. The principle: *pattern recognition supports
human judgement; it does not replace it*.

## Why these five

The five layers map cleanly to the questions any honest knowledge system
must answer:

- *How is judgement made?* — Llys.
- *What is known?* — Craidd.
- *How is what is known reasoned about?* — IDRIS.
- *What is the record of what was done and why?* — Prawf.
- *What patterns are observable, and what do they suggest?* — Craffter.

Conflating these questions — letting reasoning rewrite the record, or
letting pattern observation silently update canonical state — is what
produces opaque AI systems whose judgements cannot be traced or
overridden. Awen Weave separates the questions so each can be answered
honestly.

## How the pattern applies

This five-layer architecture is the pattern. Every instance of Awen
Weave — [Dolgellau Town Dataset](../instances/dolgellau-town-dataset.md)
today, others tomorrow — implements the same five layers, tuned to its
domain.
