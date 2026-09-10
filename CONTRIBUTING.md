# Contributing

This guide applies to every repository in the Elevated Thinking organization; an individual repository may add its own `CONTRIBUTING.md` or `README` instructions, and those take precedence where they differ.

## Ground rules

- **Be direct and be kind.** Review comments are about the work, not the person. Assume good intent and ask before assuming a mistake.
- **Never commit secrets.** No credentials, tokens, keys, connection strings, client data, or personally identifiable information, whether in code, tests, fixtures, screenshots, or commit messages. If something sensitive lands in a repository, treat it as compromised: rotate it, then tell us.
- **Don't report security issues in public.** See [our security policy](https://github.com/Elevated-Thinking/.github/blob/main/SECURITY.md) for how to report a vulnerability privately.

## Ways to contribute

- **Report a bug.** Open an issue with what you expected, what happened, and the smallest set of steps that reproduces it. Include versions, environment, and logs or screenshots where they help.
- **Propose a change.** Open an issue describing the problem before writing the solution. For anything larger than a bug fix, this saves you from building something we can't merge.
- **Improve documentation.** Corrections, clarifications, and missing setup steps are genuinely valuable and are the easiest place to start.
- **Answer questions and review pull requests.** A second set of eyes is a contribution.

Search open and closed issues first; if a matching one exists, add to it rather than opening a duplicate.

## Development workflow

`main` is always releasable. Every change reaches it through a short-lived branch and a reviewed pull request.

1. **Fork or branch.** Organization members branch directly; outside contributors fork.
2. **Branch from `main`** with a short, descriptive name: `feat/contact-form-validation`, `fix/nav-mobile-overflow`, `docs/contributing`.
3. **Install dependencies.** Let any git hooks the repository configures install along with them.
4. **Make focused commits.** Keep each commit readable on its own, and keep unrelated changes out of it.
5. **Add or update tests** alongside the change. A bug fix should include the test that would have caught it.
6. **Run the checks locally** before pushing. Anything CI will run should already pass on your machine.
7. **Update the docs** that your change makes wrong, including the `README` and anything under `docs/`.
8. **Keep your branch current** with `main`, rebasing rather than merging so the branch stays a clean series of commits.

## Commit messages

We follow [Conventional Commits](https://www.conventionalcommits.org/), because our release tooling and changelogs read them:

```
<type>(<optional scope>): <short imperative summary>

<optional body explaining what changed and why>

<optional footer: Refs #123>
```

Types:

| Type       | Use it for                                                             |
| ---------- | ---------------------------------------------------------------------- |
| `feat`     | A new capability                                                       |
| `fix`      | A bug fix                                                              |
| `docs`     | Documentation only                                                     |
| `test`     | Tests only                                                             |
| `refactor` | Restructuring that doesn't change behavior                             |
| `perf`     | A change made specifically to improve performance                      |
| `ci`       | Workflows, pipelines, and automation                                   |
| `chore`    | Everything else: dependency bumps, build config, tooling, housekeeping |
| `revert`   | Backing out an earlier commit                                          |

- Keep the summary scannable and under 72 characters. Lowercase, imperative mood, no trailing period: `fix: keep header nav consistent`, not `Fixed the header nav.`
- Explain **why** in the body. The diff already shows what.
- Reference issues in the footer with `Refs #123`, or `Closes #123` when the merge should close it.

## Pull requests

Open the pull request against `main` and keep it as small as the change allows.

Describe the problem, the approach, and anything you decided against, and link the issue it resolves. Include before and after screenshots for anything user-visible, and note accessibility implications. Call out known gaps, follow-up work, and anything you couldn't test. Open it as a draft if it isn't ready for review yet.

## Style and quality

- **Match the surrounding code.** Existing naming, structure, and comment density in the file win over personal preference.
- **Let the formatter decide formatting.** Repositories that use Prettier (or an equivalent) enforce it in a git hook and in CI. Don't hand-format, and don't reformat files you aren't otherwise changing.
- **Prefer clear over clever.** Code is read far more often than it's written.
- **Comment the why, not the what.** Explain the constraint, the workaround, the thing that will surprise the next reader.
- **Build accessibly.** Semantic markup, keyboard operability, visible focus, and sufficient contrast are requirements, not enhancements.
- **Keep dependencies few and deliberate.** Every dependency is code we ship but don't control, and it carries our security and reliability risk with it. There's no prize for reinventing a solved problem, so reach for a library when it genuinely saves work, but only one that is reputable, actively maintained, and worth what it adds to the tree.

## Releases

Releasing is a separate step on `main`, taken when the accumulated work is ready to ship, not part of the pull request that makes the change. Keep version bumps and changelog edits out of feature and fix branches. When it's time to release, `main` gets its own version-bump commit, and production deploys are driven by a `v*` tag on that commit. Version numbers follow [Semantic Versioning](https://semver.org/).

## Licensing and attribution

Unless a repository states otherwise, contributions are offered under that repository's `LICENSE`. Only submit work you have the right to contribute, and don't paste in code, assets, or content whose license or provenance you can't account for.

## Questions

If something here is unclear or you're not sure whether an idea is worth pursuing, open an issue or email [hello@elevatedthinking.co](mailto:hello@elevatedthinking.co).
