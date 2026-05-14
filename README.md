# Conventional Comments Skill

[![skills.sh](https://skills.sh/b/roziscoding/conventional-comments)](https://skills.sh/roziscoding/conventional-comments)

This repository packages an agent skill for writing Conventional Comments in pull request and merge request reviews.

The skill was derived from the badge behavior implemented by the Pullpo Conventional Comments browser extension. Thanks to Pullpo for the original extension and for making the review-comment format easier to use in everyday code review workflows.

Original project links:

- Repository: [pullpo-io/conventional-comments](https://github.com/pullpo-io/conventional-comments)
- Chrome extension: [Chrome Web Store](https://chromewebstore.google.com/detail/gelgbjildgbbfgfgpibgcnolcipinmlp)
- Firefox extension: [Firefox Add-ons](https://addons.mozilla.org/en-US/firefox/addon/conventional-comments-pullpo/)

## What It Does

The skill teaches an agent how to choose and render Conventional Comments badges for review feedback. It covers:

- Comment types such as `praise`, `nitpick`, `suggestion`, `issue`, `question`, `thought`, `chore`, and `todo`.
- Decorations such as `non-blocking`, `blocking`, and `if-minor`.
- When to use each type and decoration.
- The exact Shields.io badge markdown for every supported combination.
- Common mistakes, including incorrect colors, missing metadata links, and hyphen escaping in Shields.io URLs.

## How It Works

The main skill lives at:

```text
skills/conventional-comments/SKILL.md
```

Agents load this file when they are about to comment on a pull request or merge request, write PR review feedback, or generate Conventional Comments badge markdown.

For exact copy-ready badge markdown, the skill points agents to:

```text
skills/conventional-comments/references/matrix.md
```

That reference file contains the complete matrix of supported badge combinations.

## Use Cases

Use this skill when an agent needs to:

- Leave structured PR review comments.
- Mark feedback as blocking or non-blocking.
- Generate badge-style Conventional Comments.
- Keep review feedback consistent across GitHub, GitLab, or similar code review tools.

## Examples

### Plain Conventional Comments:

> suggestion(non-blocking): This helper could return early to keep the main path easier to scan.

> issue(blocking): This branch can write a duplicate record when the retry runs after a partial failure.

> question: Should this also handle archived projects?

### Badge-style comments:

> [![suggestion(non-blocking)](https://img.shields.io/badge/suggestion-non--blocking-9CA3AF?labelColor=3B82F6)](https://comments.example/cc?l=suggestion&d=non-blocking)
>
> This helper could return early to keep the main path easier to scan.

> [![issue(blocking)](https://img.shields.io/badge/issue-blocking-374151?labelColor=EF4444)](https://comments.example/cc?l=issue&d=blocking)
>
> This branch can write a duplicate record when the retry runs after a partial failure.

> [![question](https://img.shields.io/badge/question-8B5CF6)](https://comments.example/cc?l=question)
>
> Should this also handle archived projects?

The skill also includes a full badge matrix at [references/matrix.md](skills/conventional-comments/references/matrix.md).

## Installation

Install it with your preferred package runner:

```bash
npx skills add roziscoding/conventional-comments
pnpx skills add roziscoding/conventional-comments
bunx skills add roziscoding/conventional-comments
```

You can also copy the skill directory into your agent skills folder manually:

```text
skills/conventional-comments
```

The exact destination depends on your agent runtime. The important part is that the directory containing `SKILL.md` is available as a skill named `conventional-comments`.

## License

MIT
