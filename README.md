# encyclopedia

A machine-readable knowledge graph for building systems with AI agents — where
the **model is the source of truth**, maturity is **computed, never claimed**,
and "done" is only ever the verdict of a mechanical gate.

## Why this exists

Five weeks of agent-built infrastructure ([k8s-platform forensics](https://github.com/lago-morph/k8s-platform/tree/main/forensics))
produced one empirical law: **mechanical enforcement ended every bug class it
was applied to; prose rules ended none.** This repo is methodology rebuilt
under that law: as much structure as we like, provided every element is
something a machine can check, compute, or refuse. Structure maximalism,
prose minimalism.

It revives the CASE-encyclopedia idea (IEF, AD/Cycle) with the two failure
causes inverted: generated artifacts are never hand-edited, and agents keep
the model current. Conceptual debts: OMG Essence (alpha states as
machine-checkable cards), RUP/RMC (method content vs. process), consumer-driven
contracts, spec-by-example.

## How it works

Everything is a typed **node**: one YAML file in `nodes/`, wearing the common
envelope defined in `schema/envelope.yaml`. Relationships are typed edges
(`schema/edges.yaml`) with explicit change-propagation semantics. Node kinds
live in `schema/kinds.yaml`.

Every node carries a computed **maturity level**:

| Level | Meaning | Bar |
|---|---|---|
| L0 | stub | id + intent + serves edge |
| L1 | sketched | shape exists; no machine-checkable criteria yet |
| L2 | checkable | machine-checkable criteria exist and pass |
| L3 | verified | proven against reality, from clean, repeatably |

**The L1 ceiling rule:** a node with no machine-checkable criterion can never
exceed L1 — no matter how good its prose is. This is the firewall against the
documented failure mode of elaborate specs that nothing can falsify.

## State of this graph

Almost everything here is **L0 — deliberately**. The vision is captured as
cheap stubs so it persists and can be seen whole; slices are then driven up
the ladder one rung at a time. A mostly-grey map with one bright slice is
honest. A fully-bright map on day one would be the old disease.

## Working agreement

The operating agreement is itself a node: [`nodes/wow-0001.yaml`](nodes/wow-0001.yaml).
Settled choices are decision nodes (`nodes/dec-*.yaml`) with provenance.
Open modeling questions live in [`OPEN-QUESTIONS.md`](OPEN-QUESTIONS.md).

## Next

First slice: the loader + linter (`com-0001`) — the machinery that makes every
claim above enforceable instead of aspirational.
