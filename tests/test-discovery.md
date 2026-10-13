# Discovery tests

Checks that findable activates for publisher-side requests and stays out of the way of skill-authoring and reverse-search skills. Run with findable installed alongside skill-creator.

## Should activate findable

- "How do I get more stars and traffic for my repo?"
- "Another repo with the same name shows up instead of mine. What do I do?"
- "I'm about to publish a skill. Set up its GitHub listing."
- "Write the About text and topics for my MCP server."
- "Draft a page for my skill for my website."
- "Which directories should I submit my plugin to?"

## Should not activate findable

- "Find me a good skill for reviewing resumes." (reverse problem: searching, not publishing)
- "Which GitHub repos are alternatives to X?" (repo search)
- "Make my skill trigger more reliably in Claude Code." (skill-creator: tuning a SKILL.md description)
- "Write the SKILL.md for my new skill." (skill-creator: authoring)
- "Make this README more readable." (general editing, no discovery goal)

## Ambiguous: expected routing

| Prompt | Expected routing |
|---|---|
| "Publish my skills so installers can find them from my domain." | findable for the listing and project pages, and a pointer to the discovery-index mechanism (`skills-visibility` or the current spec) for the index itself |
| "Promote my repo on Reddit." | findable's distribution rules: disclose authorship, lead with a real example, no star requests |
| "Improve my skill's description." | Ask which audience: agent triggering goes to skill-creator; search and directory copy stays in findable |
