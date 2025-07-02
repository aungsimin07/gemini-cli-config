# Conventional Commit Guidelines

This document outlines the guidelines for writing commit messages that adhere to the Conventional Commits specification. These guidelines will help ensure consistent, readable, and informative commit history.

## Commit Message Structure

Commit messages MUST be structured as follows:

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

## Structural Elements

### Type (Required)

The type MUST be a noun and indicates the nature of the change.

-   **`feat`**: A new feature is introduced to the codebase. (Correlates with `MINOR` in Semantic Versioning).
-   **`fix`**: A bug fix in the codebase. (Correlates with `PATCH` in Semantic Versioning).
-   **Other Allowed Types**:
    -   `build`: Changes that affect the build system or external dependencies (e.g., npm, gulp)
    -   `chore`: Routine tasks, maintenance, or minor changes that don't affect the meaning of the code (e.g., updating dependencies, refactoring without behavior changes)
    -   `ci`: Changes to CI configuration files and scripts (e.g., Travis, Circle, BrowserStack, SauceLabs)
    -   `docs`: Documentation only changes
    -   `style`: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc.)
    -   `refactor`: A code change that neither fixes a bug nor adds a feature
    -   `perf`: A code change that improves performance
    -   `test`: Adding missing tests or correcting existing tests

### Scope (Optional)

A scope MAY be provided after the type, enclosed in parentheses. It should be a noun describing a section of the codebase.
Example: `feat(parser): add ability to parse arrays`

### Description (Required)

A short, imperative summary of the code changes. It MUST immediately follow the colon and space after the type/scope prefix.
Example: `fix: array parsing issue when multiple spaces were contained in string`

### Body (Optional)

A longer commit body MAY be provided after the short description, providing additional contextual information about the code changes. The body MUST begin one blank line after the description and can consist of any number of newline separated paragraphs. When committing from the command line, you can use multiple `-m` flags for each line of the body.

### Footers (Optional)

One or more footers MAY be provided one blank line after the body. Each footer MUST consist of a word token, followed by either a `:<space>` or `<space>#` separator, followed by a string value. Footer tokens MUST use `-` in place of whitespace characters (e.g., `Acked-by`).

#### Breaking Changes

Breaking changes MUST be indicated in one of two ways:

1.  **In the type/scope prefix**: Append a `!` immediately before the `:`. If `!` is used, `BREAKING CHANGE:` MAY be omitted from the footer section, and the commit description SHALL be used to describe the breaking change.
    Example: `feat!: send an email to the customer when a product is shipped`
    Example with scope: `feat(api)!: send an email to the customer when a product is shipped`
2.  **As a footer entry**: Consist of the uppercase text `BREAKING CHANGE`, followed by a colon, space, and description.
    Example: `BREAKING CHANGE: environment variables now take precedence over config files`

A `BREAKING CHANGE` can be part of commits of any type and correlates with `MAJOR` in Semantic Versioning.

## Examples

### Commit message with description and breaking change footer

```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

### Commit message with `!` to draw attention to breaking change

```
feat!: send an email to the customer when a product is shipped
```

### Commit message with scope and `!` to draw attention to breaking change

```
feat(api)!: send an email to the customer when a product is shipped
```

### Commit message with both `!` and BREAKING CHANGE footer

```
chore!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

### Commit message with no body

```
docs: correct spelling of CHANGELOG
```

### Commit message with scope

```
feat(lang): add Polish language
```

### Commit message with multi-paragraph body and multiple footers

```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```
