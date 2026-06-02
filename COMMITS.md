# Commit Guidelines

This repository follows the [Conventional Commits v1.0.0](https://www.conventionalcommits.org/en/v1.0.0/) specification.

## Structure

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

## Types

| Type       | Use for                                                        | SemVer |
|------------|----------------------------------------------------------------|--------|
| `feat`     | A new feature                                                  | MINOR  |
| `fix`      | A bug fix                                                      | PATCH  |
| `docs`     | Documentation-only changes                                     | —      |
| `style`    | Formatting, whitespace, semicolons (no code-meaning change)    | —      |
| `refactor` | Code change that neither fixes a bug nor adds a feature        | —      |
| `perf`     | A change that improves performance                             | —      |
| `test`     | Adding or correcting tests                                     | —      |
| `build`    | Build system or external dependency changes                    | —      |
| `ci`       | CI configuration and scripts                                   | —      |
| `chore`    | Other changes that don't modify src or test files             | —      |

## Rules

1. Commits **MUST** be prefixed with a type, followed by an optional scope, an optional `!`, and a required colon and space.
2. `feat` **MUST** be used when a commit adds a new feature.
3. `fix` **MUST** be used when a commit is a bug fix.
4. A scope **MAY** be provided in parentheses for context: `feat(parser): ...`.
5. A description **MUST** immediately follow the colon and space.
6. A longer body **MAY** be provided one blank line after the description.
7. Footers **MAY** be provided one blank line after the body, using the git trailer convention (`Token: value`).
8. Breaking changes **MUST** be indicated either by a `!` before the colon, or a `BREAKING CHANGE:` footer (or both).
9. `BREAKING CHANGE` **MUST** be uppercase. All other units are case-insensitive.

## Examples

Minimal:

```
docs: correct CHANGELOG spelling
```

With scope:

```
feat(lang): add Polish language
```

Breaking change via `!`:

```
feat!: drop support for Node 6
```

Breaking change via footer:

```
feat: allow config object to extend other configs

BREAKING CHANGE: `extends` key now used for extending config files
```

With body and footers:

```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
responses other than from the latest request.

Reviewed-by: Z
Refs: #123
```
