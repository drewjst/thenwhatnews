# Ripple Atlas

Ripple Atlas is a globe-first news atlas for tracing what happened, where, and
what changed as a result. A reader starts with an event such as a weather
system, follows a documented closure or response to a specific place, and
inspects the source behind each step. An agent traverses the same graph to
produce a cited briefing or to count distinct affected events across a region.

## Status

This repository holds an interaction mockup. Every story, evidence record, and
weather footprint in it is fictional. No ingestion, database, or API exists
here.

## Try the mockup

Open `index.html` in a browser. The file is self-contained and makes no network
requests.

The mockup demonstrates the following interactions:

- **Globe**: rotate, zoom, and drill down from North America to a county.
- **Weather layer**: show or hide the footprint of a weather system.
- **Graph view**: follow connections between stories across one to three hops.
- **Connection explanations**: read why two stories are linked and which source
  record supports the link.
- **Graph query**: copy or download the same graph as agent-readable JSON.

## Design principles

The following principles guide the design:

- **Evidence is separate from events.** A source revision, an event revision,
  and a relationship revision are distinct records with their own history.
- **Every link earns its place.** A causal link needs a source passage that
  supports that specific step. Proximity, dates, and similarity only find
  candidates for review.
- **Three clocks stay separate.** Occurrence time, source publication time, and
  atlas review time are never merged.
- **Corrections are first class.** A changed link supersedes its old revision
  and identifies every briefing that cited it.
- **Readers and agents see the same claims.** The JSON interface returns the
  same published claims and provenance that the globe shows.
- **Code does the deterministic work.** Code handles fetching, hashing, time
  normalization, geography, traversal, and counts. A model proposes claims and
  matches. An editor decides what publishes.

## License

Copyright (C) 2026 Andrew (drewjst).

Ripple Atlas is free software. You can redistribute it and modify it under the
terms of the GNU Affero General Public License, version 3 only, as published by
the Free Software Foundation. For the full text, see [LICENSE](LICENSE).

If you run a modified version as a network service, the license requires you to
offer the modified source to the users of that service.

The license covers the code and content in this repository. It doesn't grant
any right to use the name "Ripple Atlas" or the project's logo for a derived
product or service.

To use this work under different terms, open an issue to ask about a commercial
license.

## Third-party material

The mockup embeds the following third-party material:

- **DM Sans** and **Instrument Serif**: SIL Open Font License 1.1. The license
  text is embedded at the end of `index.html`.
- **Natural Earth** boundaries: public domain.
- **U.S. Census Bureau** cartographic boundaries: public domain.
