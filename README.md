### Find filename with an optional non-capturing digit suffix

```
/filename(?:[0-9]{1,3})?\.ext/
```

#### Explanation:

-   **`filename`**: Matches the literal string "filename".
-   **`(?:[0-9]{1,3})?`**: Optionally matches between 1 and 3 digits.
    -   **`(?:...)`** makes it a non-capturing group.
    -   **`{1,3}`** specifies one to three digits.
-   **`\.ext`**: Matches the literal string ".ext" (dots are escaped).

This regex will match both "filename.ext" and "filename001.ext".

### Find part of a class name in any HTML class declaration

```
class="([^"]*\b)(name\b)(\b[^"]*)"
```

#### Explanation:

-   **`([^"]*\b)`**: Matches any characters that are not double quotes followed by a word boundary before `name`.
-   **`(name\b)`**: Matches the literal word `name` with a word boundary on both sides.
-   **`(\b[^"]*)`**: Matches a word boundary after `name` followed by any characters that are not double quotes.

This creates three separate capture groups, allowing you to access each part of the matched string as needed.

### Find Bootstrap/Tailwind spacing classes

```
^[pm][xytbes]?-(xs-|sm-|md-|lg-|xl-)?$
```

#### Explanation:

-   **`^`**: Asserts the beginning of the string.
-   **`[pm]`**: Matches either 'p' or 'm'.
-   **`[xytbes]?`**: Matches zero or one occurrence of 'x', 'y', 't', 'b', 's', or 'e'.
-   **`-`**: Matches the hyphen.
-   **`(xs-|sm-|md-|lg-|xl-)?`**: Matches zero or one occurrence of the specified three-character patterns.
-   **`$`**: Asserts the end of the string.

This regular expression ensures that the string follows the pattern:

-   First character (mandatory): 'p' or 'm'
-   Second character (optional): 'x', 'y', 't', 'b', 's' or 'e'
-   Third character: Hyphen '-'
-   Fourth, fifth and sixth characters (optional): 'xs-', 'sm-', 'md-', 'lg-' or 'xl-'

### Find all hrefs that reference relative paths

```
href="(?!(?:http|https|mailto|tel|[\{#%']))
```

#### Explanation:

-   **`href="`**: Matches the literal string.
-   **`(?!(?:http|https|mailto|tel|[\{#%']))`**: Negative lookahead that ensures the text following `href="` does not start with:
    -   the substrings `http`, `https`, `mailto` and `tel`, or
    -   the characters `{`, `#`, `%` and `'`.

This regex will match `href="` only when it is not immediately followed by any of the disallowed tokens.
