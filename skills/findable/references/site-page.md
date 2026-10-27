# A page for the project on the user's own site

A project page on a domain the user controls is the one discovery surface that is fully theirs. It can rank for the task queries, give directories and AI assistants something to cite, and link the repo and the site to each other.

Make one page per project, not one page for everything. Write it as portable Markdown with simple frontmatter, because the site's stack is usually unknown. If the user shares the stack or an existing page, match its conventions.

## Template

````markdown
---
title: "<name>: <task phrase> for <platform>"
description: "<one sentence: what it does, for whom, the guarantee>"
slug: <name>
repo: https://github.com/OWNER/REPO
install: "<one copy-paste install command>"
tags: [<tags drawn from the repo topics>]
---

# <name>: <task phrase>

<Opening paragraph: what it is, who it is for, what it will and will not do. Use the phrases from the target queries.>

## What you can ask it

<A table of commands, modes or tools, one line each, taken from the repo. Do not add anything the repo does not do.>

## Install

<Primary install command in a code block. Then the other real options: plugin marketplace, manual copy, with the directories to copy into.>

## Example

[Paste a real output here, taken from the repo's examples. A real before-and-after is the strongest thing on the page.]

## Questions

**<Question a skeptical reader would ask first>**
<Short, true answer.>

**Is it related to <same-name project>?**
<Only if a same-name project exists. One sentence on what each one is and that they are unrelated.>

## Related

- <Sibling project, one line on how they differ>
- [Source on GitHub](https://github.com/OWNER/REPO)
````

## When the collision is the site's brand

If same-name sites on other domains own the brand search (the audit's name-plus-domain query), the project page alone will not fix it; the site's homepage carries the brand. Draft, for the user to apply:

- **Homepage title** with the brand and a qualifier only this site can claim, such as the domain or the maker (`Skillsmith (skillsmith.tech): ...` or `Skillsmith by Caffeinity: ...`), so the result is distinguishable at a glance.
- **Structured data** on the homepage: `WebSite` with `alternateName` listing the domain and the qualified name, and an `Organization` with `sameAs` links to profiles that are really the same entity (never to the same-name projects). Pages elsewhere on the site reuse the same `@id`s rather than declaring new entities.
- **A disambiguation line** in the homepage FAQ or footer: what this site is, and that it is not the same-name projects, each named with its domain. Only state it when the user confirms the projects are unrelated.
- **A real favicon** at the site root. Search results show it beside the domain, and a generic globe icon makes a brand result look like any other.

Check these against `references/audit.md` section 0 first: if the domain is not indexed, none of this is visible yet.

## Rules

- **Title** up to about 70 characters and **description** up to about 155, so search snippets are not cut off. Put the task phrase first, then the platform.
- **One H1**, matching the title's task phrase. Use real headings and tables rather than images of text.
- **The Example slot is for real output.** Never invent a sample. If the user has none, say the page should wait for one, or build it from a real run.
- **FAQ answers must be true.** The strongest FAQ entries state limits plainly: what the project does not do, what it never fabricates, how it differs from siblings and same-name projects.
- **Link both ways.** The page links to the repo; the repo's homepage field links to the page; sibling pages link to each other.
- **Match the repo.** Install commands, command names and supported agents must be the same as the README, character for character.
- **Optional:** structured data (for example a `SoftwareSourceCode` block) and an entry in the site's sitemap. Only add what the site already supports.
- If the site hosts several skills, consider the machine-readable discovery index described at the end of SKILL.md, so installers can resolve the skills from the domain.
