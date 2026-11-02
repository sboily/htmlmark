# Changelog

## 0.1.0 (unreleased)

First release.

- `convert` turns an HTML document into CommonMark, with GitHub-flavored pipe
  tables and strikethrough, or into its visible words.
- `Options` bound the parsed document (`max_nodes`, `max_depth`) and the output
  (`max_output_bytes`, checked on every write), rewrite link and image URLs,
  and poll an `interrupt` callback between parser chunks, every few hundred
  rendered nodes and every few thousand lines of a code block.
- Text that would read as Markdown syntax is escaped, and emphasis is written
  only where a CommonMark reader shows it as emphasis.
