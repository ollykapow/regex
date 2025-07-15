### Find all hrefs that reference relative paths

`href="(?!(?:http|https|mailto|tel|[\{#%']))`

#### Explanation

-   `href="` matches the literal string.
-   `(?!(?:http|https|mailto|tel|[\{#%']))` is a negative lookahead that ensures the text following `href="` does not start with:
    -   the substrings `http`, `https`, `mailto` and `tel`, or
    -   the characters `{`, `#`, `%` and `'`.

This regex will match `href="` only when it is not immediately followed by any of the disallowed tokens.
