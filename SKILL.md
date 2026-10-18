---
name: marketplace-publish
description: Prepare software projects for CodeCanyon or Picalica with marketplace-specific listings, pricing, buyer documentation, presentation assets and source packages. Use for تجهيز مشروع للنشر على بيكاليكا أو كودكانون, preparing a marketplace submission, or updating an existing publishing package.
---

# Marketplace publishing preparation

Prepare a reviewable submission package grounded in the actual project and the selected marketplace's current rules. Preparation does not itself authorize marketplace submission, terms acceptance, account changes or messages to other people.

## Resolve the request

Read repository instructions and existing publishing materials. Carry forward the user's latest platform, price, language and destination choices. Ask only for missing choices that materially affect the result; continue independent preparation while awaiting them.

- Honor the exact requested output folder, including unconventional spelling. Otherwise use `docs/codecanyon-publish/` or `docs/picalica-publish/`, with separate folders for separate platforms.
- Interpret a general price as the buyer-visible target before taxes unless context says otherwise. State that interpretation. Leave unchosen additional license prices unset, or clearly mark a proposed value for review.
- For this repository, obtain the latest price and folder choices from its publishing metadata and user messages; do not turn them into defaults for other projects.
- For a price-only follow-up, update the relevant metadata, prose and calculations. Inspect archive contents and rebuild only artifacts that contain changed material; preserve historical test outcomes. Avoid rerunning application tests for editorial price changes.

## Inspect evidence and platform rules

Inspect package metadata, entrypoints, modules, localization, database, payments, licensing, platform runners and existing tests. Separate implemented behavior from README claims, placeholders and unverified compatibility. Check a linked competitor's public presentation when supplied; write original copy without borrowing its assets or descriptions.

Read only the reference for each requested platform:

- **CodeCanyon:** [references/codecanyon.md](references/codecanyon.md).
- **Picalica / بيكاليكا:** [references/picalica.md](references/picalica.md).

Browse official sources to verify current requirements, fees, license distinctions, images, documentation, support and account eligibility. Record source links and the date checked. If a form is inaccessible, use official public guidance and identify fields that remain unverified. Do not infer account access or submitter eligibility from a public help article.

Complete this stage when each material selling claim has project evidence and each platform-dependent requirement has a source or an explicit unresolved status.

## Produce the publishing materials

Adapt the file set to the request and reuse valid existing work. A full preparation normally includes:

- A concise `README.md` indexing the deliverables and their readiness.
- `submission.json` with title, summary, category, tags, version, source stack, license prices, exclusivity, asset paths and unresolved fields. Use JSON `null` or explicit draft status for unknown values.
- Original listing copy in the platform's language and format, distinguishing the source product from an installed/hosted service.
- An offline HTML buyer guide covering installation, first run, credentials/onboarding, usage, backup/restore, customization, actual APIs and credits. Arabic guides use `lang="ar"` and `dir="rtl"`; technical commands remain readable left-to-right.
- Pricing/license notes, release notes, a sourced platform-requirements note and a prioritized upload/readiness checklist. Keep internal research out of buyer downloads.
- Presentation assets and an actual-screen capture plan. A designed cover or a screenshot of documentation does not count as an application screenshot. Reuse only cleared assets; render and inspect generated graphics and guides.

Keep the price authoritative in metadata and reconcile every active description, note and calculation when it changes. Label financial amounts as estimates where taxes, category fees or other deductions remain unknown. Verify asset rights and required notices for the exact bundled files, not merely the existence of their upstream websites.

Surface incompatible activation, payment stubs, signing gaps, default credentials and unsupported platform claims before drafting promises. A publishing-materials request does not automatically authorize removing a paid activation mechanism or changing product licensing. Prepare the materials, identify the specific conflict, and obtain direction before a material product change outside the established scope.

## Package and verify

Build a source archive when requested or useful for the submission. Use an explicit source allowlist appropriate to the stack. Exclude repository history, private keys/license-signing tools, credentials, personal data, local machine configuration, downloaded dependency caches and unrelated outputs. Retain generated source required to compile, the lockfile, buyer documentation and applicable notices. Excluding the signing tool does not remove an application's activation requirement.

Prefer a standalone build of the current candidate. Reuse an earlier source archive only after checking its integrity, version, exact source file set and hashes against the current project. Attribute reused test results to their original run. Platform-specific documentation must not depend on another marketplace's files in the buyer ZIP.

Verify JSON, price arithmetic, local links, document language/layout, image dimensions, archive paths/integrity and packaged content. Run meaningful application checks when preparing a new source release or changing code. Verify advertised platforms through appropriate release builds and fresh-install acceptance. If dependencies stall, preserve the log, stop only this task's processes and report the actual stage reached; a download failure is not a compiler result.

Create a concise verification record distinguishing new checks, inherited evidence and work not performed. Use a candidate filename/status while readiness requirements remain unresolved. Preserve earlier archives instead of silently replacing them.

## Handoff

Link the package index and important artifacts. State the selected price and any additional proposed license price, summarize verification and identify remaining publication blockers. Distinguish materials prepared, release verified and product published. Perform external submission or other account actions only when separately authorized and the concrete submission is ready for review.

Example invocation:

```text
Use $marketplace-publish to prepare this project for Picalica and CodeCanyon
with a $50 general price. Put the files in docs/picalica-publish/ and
docs/codecanyon-publish/.
```
