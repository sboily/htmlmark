# Security policy

`htmlmark` is meant for HTML nobody vouches for, so these are security bugs:

- a panic, a stack overflow or an abort on any input;
- work or memory that grows faster than the input, or that `max_nodes`,
  `max_depth`, `max_output_bytes` or the `interrupt` callback do not bound;
- output larger than `max_output_bytes`;
- Markdown that a CommonMark reader shows differently from the page's visible
  text: raw HTML, a link or image the page did not have, or text turned into
  markup.

Report them privately through
[GitHub's private vulnerability reporting](https://github.com/sboily/htmlmark/security/advisories/new),
with the input that shows the problem. Please do not open a public issue for
them. Fixes go into the latest release only.
