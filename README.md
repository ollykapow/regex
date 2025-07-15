### Find part of a class name in any HTML class declaration

`class="([^"]*\b)(name\b)(\b[^"]*)"`

#### Explanation

-   `([^"]*\b)` matches any characters that are not double quotes followed by a word boundary before `name`.
-   `(name\b)` matches the literal word `name` with a word boundary on both sides.
-   `(\b[^"]*)` matches a word boundary after `name` followed by any characters that are not double quotes.

This creates three separate capture groups, allowing you to access each part of the matched string as needed.

### Find Bootstrap/Tailwind spacing classes

`^[pm][xytbes]?-(xs-|sm-|md-|lg-|xl-)?$`

#### Explanation

Explanation:

-   `^`: Asserts the beginning of the string.
-   `[pm]`: Matches either 'p' or 'm'.
-   `[xytbes]?`: Matches zero or one occurrence of 'x', 'y', 't', 'b', 's', or 'e'.
-   `-`: Matches the hyphen.
-   `(xs-|sm-|md-|lg-|xl-)?`: Matches zero or one occurrence of the specified three-character patterns.
-   `$`: Asserts the end of the string.

This regular expression ensures that the string follows the pattern:

-   First character (mandatory): 'p' or 'm'
-   Second character (optional): 'x', 'y', 't', 'b', 's' or 'e'
-   Third character: Hyphen '-'
-   Fourth, fifth and sixth characters (optional): 'xs-', 'sm-', 'md-', 'lg-' or 'xl-'

### Find all hrefs that reference relative paths

`href="(?!(?:http|https|mailto|tel|[\{#%']))`

#### Explanation

-   `href="` matches the literal string.
-   `(?!(?:http|https|mailto|tel|[\{#%']))` is a negative lookahead that ensures the text following `href="` does not start with:
    -   the substrings `http`, `https`, `mailto` and `tel`, or
    -   the characters `{`, `#`, `%` and `'`.

This regex will match `href="` only when it is not immediately followed by any of the disallowed tokens.
