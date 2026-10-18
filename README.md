# Marketplace Publish

A reusable Codex skill for preparing software projects for **CodeCanyon** and **Picalica (بيكاليكا)**. It reviews the actual project and current marketplace requirements, then prepares listings, pricing, buyer documentation, presentation assets and source packages.

This repository contains the skill only. Your application's publishing files are generated in the project and folders you specify.

## Install from GitHub

The repository is **private**. Your GitHub account must have access. For Git-based installation, authenticate through your configured Git credentials or SSH; GitHub CLI users can use `gh auth login` and, when needed, `gh auth setup-git`. Do not paste access tokens into prompts or repository URLs.

### Option 1: Ask Codex to install it

Use the built-in installer in a Codex conversation:

```text
$skill-installer Install marketplace-publish from
https://github.com/enghany301096/marketplace-publish
using branch main. The skill is at the repository root (path .).
Install it with the name marketplace-publish.
```

The explicit name matters because `SKILL.md` is at the repository root. The bundled installer uses your configured Codex skills directory and refuses to overwrite an existing installation.

### Option 2: Clone it manually

For macOS, Linux or WSL, run:

```sh
mkdir -p "$HOME/.agents/skills"
git clone --branch main --single-branch \
  https://github.com/enghany301096/marketplace-publish.git \
  "$HOME/.agents/skills/marketplace-publish"
```

Use one installation method to avoid duplicate skills. Codex discovers skills from `~/.agents/skills`; existing installations in a configured Codex skills directory can remain where they are. If the skill does not appear, restart Codex. See the [official skills guide](https://learn.chatgpt.com/docs/build-skills).

## Use it in your project

Open the application project in Codex and mention `$marketplace-publish`. Specify the marketplace, buyer-visible price and output folder. Include a competitor URL if you want its public presentation reviewed.

**Both marketplaces:**

```text
$marketplace-publish Prepare this project for CodeCanyon and Picalica
with a $50 general price. Save CodeCanyon files in docs/codecanyon-publish/
and Picalica files in docs/picalica-publish/.
```

**بيكاليكا بالعربية:**

```text
$marketplace-publish جهّز المشروع للنشر على بيكاليكا بسعر عام 50 دولارًا.
احفظ الملفات في docs/picalica-publish/، وجهّز الوصف والدليل بالعربية.
```

**Update an existing package:**

```text
$marketplace-publish Change the general price to $75 in the existing
publishing packages and update the related fee calculations and text.
```

Prices in these examples are inputs, not skill defaults. CodeCanyon's list price and author entry differ; Picalica's personal and commercial licenses have separate fields. The skill records its interpretation and flags unchosen license prices for review.

## What it prepares

- Product metadata, original listing copy and marketplace-specific pricing notes.
- Offline buyer documentation, including Arabic/RTL for Picalica.
- Cover artwork and a plan for genuine application screenshots.
- Source ZIPs, dependency notices and verification records when appropriate.
- A sourced checklist of missing requirements and publication blockers.

The skill checks current platform rules rather than relying on fixed fees or image sizes. Generated covers are not application screenshots. Activation requirements, unverified platforms, payment stubs and asset-rights gaps are reported explicitly. Preparing files does not publish the product or authorize account changes.

## Update your installation

If you used the manual Git clone above:

```sh
git -C "$HOME/.agents/skills/marketplace-publish" pull --ff-only origin main
```

For a clone in another location, use that path. If Git reports local edits or divergence, review those changes before updating; do not force-reset them.

For an installer-created copy without Git history, ask Codex to update it from this repository while preserving local customizations. The installer does not overwrite an existing folder; keep any backup outside active skill-discovery directories. Codex detects skill changes automatically; restart it if an update is not visible.

## Skill files

| File | Purpose |
| --- | --- |
| [SKILL.md](SKILL.md) | Main workflow and invocation rules |
| [references/codecanyon.md](references/codecanyon.md) | CodeCanyon decisions and official source links |
| [references/picalica.md](references/picalica.md) | Picalica decisions and official source links |
| [agents/openai.yaml](agents/openai.yaml) | Skill display information and example prompt |
