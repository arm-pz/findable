# findable

An agent skill that sets up discovery for a GitHub repo, agent skill, Claude Code plugin or MCP server. It audits where your project shows up in search, then writes the GitHub About text, topics, README opening, release notes and a project page for your site, lists the directories worth submitting to, and plans a re-check. It never games stars.

Install: `npx skills add arm-pz/findable --skill findable`

Ask it things like:

- "Set up discovery for github.com/me/my-skill."
- "Why does another repo with the same name show up instead of mine?"
- "Write the About text and topics for my MCP server."
- "Draft a page for my skill for my website."

## What you get

| Step | Output |
|---|---|
| Audit | A baseline: name searches, task searches, same-name projects, repo metadata gaps |
| Target queries | Five to ten queries a stranger would type, none that need the project name |
| Name decision | Keep and qualify the name, or rename, with the cost of each |
| GitHub listing | About text, topics, homepage, release notes, social preview brief |
| README opening | First paragraph, install line, example prompts, disambiguation line |
| Project page | Portable Markdown page for your own site, with a slot for a real example |
| Distribution | Directories and lists to check, entry text, honest community-post rules |
| Re-check | A dated plan to re-run the baseline queries |

`scripts/check_listing.py` checks the About text, topics and page titles against GitHub and search-snippet limits.

## Not for

Finding repos or skills for a task (the reverse problem), authoring a SKILL.md, or tuning a skill's description so an agent triggers it better. Use skill-creator for the last two. To publish a multi-skill catalog index on your own domain (`/.well-known/agent-skills/index.json`), see Evil Martians' `skills-visibility` skill; findable points to that mechanism rather than duplicating it. findable is not affiliated with it.

## Install

```
npx skills add arm-pz/findable --skill findable
```

Or copy `skills/findable/` into your agent's skills directory (`.claude/skills/`, `.agents/skills/`, `.cursor/skills/` or `.qoder/skills/`). With Claude Code plugins, `.claude-plugin/plugin.json` makes the repo installable as a plugin; add it to your marketplace repo as an entry pointing at `arm-pz/findable`.

## Structure

```
findable/
├── README.md
├── .claude-plugin/
│   └── plugin.json
├── skills/
│   └── findable/
│       ├── SKILL.md            # workflow, ground rules, kit format
│       ├── references/
│       │   ├── audit.md        # baseline procedure
│       │   ├── listing.md      # About, topics, README opening, releases
│       │   ├── site-page.md    # project page template and rules
│       │   └── distribution.md # directories, entry text, honest promotion
│       └── scripts/
│           └── check_listing.py
└── tests/
    ├── test-discovery.md
    └── test-prompts.md
```

## Credits

The discovery-index pointer draws on Evil Martians' write-up of the `.well-known/agent-skills/index.json` mechanism. Verify the current spec before relying on it.
