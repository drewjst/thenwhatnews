# Then What News

Then What News captures news, shows where in the world it happens, and links
each event to what followed it. A hurricane hits Florida. Then what? Months
later, insurers raise prices. A bill cuts a health program. Then what? Later
stories report people who can't get care.

The links come from software, not from an editor. The pipeline is designed to
run on its own: it collects stories, places them on a globe, groups them into
events, and connects the events that follow from one another.

## Status

This repository holds an interaction mockup. Every story, evidence record, and
weather footprint in it is fictional. No pipeline, database, or API exists
here.

## Try the mockup

Open the [live mockup](https://drewjst.github.io/thenwhatnews/), or open
`index.html` in a browser. The file is self-contained and makes no network
requests.

The mockup demonstrates the following interactions:

- **Globe**: rotate, zoom, and drill down from North America to a county.
- **Weather layer**: show or hide the footprint of a weather system.
- **Graph view**: follow connections between stories across one to three hops.
- **Connection explanations**: read why two stories are linked and which source
  record supports the link.
- **Graph query**: copy or download the same graph as agent-readable JSON.

## How it is meant to work

The pipeline has the following stages:

1. **Capture**: fetch stories from news and official feeds. Store the headline,
   the link, the publisher, the publication time, and a short quote.
2. **Locate**: place each story on the map, and record how precise the location
   is.
3. **Cluster**: group the stories that describe one event.
4. **Link**: propose pairs of events that might be connected, and classify each
   pair.
5. **Publish**: write the graph that the globe and the JSON interface read.

## Two graphs

The product keeps two graphs:

- **Instance graph**: one event, a later event, and the link between them, with
  the source behind the link.
- **Pattern graph**: a kind of event, the kind of event that tends to follow
  it, how often, and after how long. This graph answers "what followed the last
  nine events like this one?"

## What a link claims

A link between two events carries one of three labels:

- **Followed**: the second event came after the first, and the same sequence
  appears in past cases. This label makes no claim about cause.
- **Related**: the two events share people, organizations, places, or a
  document such as a bill.
- **Attributed**: a named source says that the first event led to the second.
  The link shows the quote, and the claim belongs to the source.

The software never states a cause in its own voice. An attributed link
publishes only if the quoted passage appears in the source, and code makes that
check.

## Design principles

The following principles guide the design:

- **No editor in the loop.** A test set of known true links and plausible false
  links measures the pipeline. A link type publishes automatically only while
  it passes that test.
- **Evidence is separate from events.** A source, an event, and a link are
  distinct records with their own history.
- **Links span months.** An effect can arrive long after its trigger, and it can
  arrive as a trend across many stories instead of as one event.
- **Disagreement is recorded.** A link holds the sources that support it and the
  sources that dispute it.
- **Three clocks stay separate.** The time an event happened, the time a source
  published, and the time the pipeline processed it are never merged.
- **Corrections are first class.** A changed link replaces its old version and
  keeps the history.
- **Readers and agents see the same claims.** The JSON interface returns the
  same links and sources that the globe shows.
- **Code does the deterministic work.** Code handles fetching, hashing, time
  normalization, geography, traversal, and counts. A model handles extraction
  and classification.

## Later: predictions

The pattern graph can turn an event into a question: "This kind of event was
followed by that kind of event in seven of nine past cases. Does it happen
again within six months?" Readers vote on the question, and the pipeline
resolves it when the later story arrives.

## License

Copyright (C) 2026 Andrew (drewjst).

Then What News is free software. You can redistribute it and modify it under
the terms of the GNU Affero General Public License, version 3 only, as
published by the Free Software Foundation. For the full text, see
[LICENSE](LICENSE).

If you run a modified version as a network service, the license requires you to
offer the modified source to the users of that service.

The license covers the code and content in this repository. It doesn't grant
any right to use the name "Then What News" or the project's logo for a derived
product or service.

To use this work under different terms, open an issue to ask about a commercial
license.

## Third-party material

The mockup embeds the following third-party material:

- **DM Sans** and **Instrument Serif**: SIL Open Font License 1.1. The license
  text is embedded at the end of `index.html`.
- **Natural Earth** boundaries: public domain.
- **U.S. Census Bureau** cartographic boundaries: public domain.
