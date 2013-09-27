### Smart References

This ConTeXt module simplifies and automates references to floats or sections.
It has the same semantics as `\in` and takes the same arguments. At the moment
it provides the single command `\smartref`, which is basically `\in`, `\at`
and `\atpage` merged together into one single command. Here is an example:

    \smartref{figure}[fig:somefigure]

The existing commands are not flexible enough. `\atpage` does not have the
concept of double pages. This means it might, for instance, print
\quotation{as we show above} even if the float is visible. `\somewhere`
doesn't suppress the reference text if the reference happens to end up on the
same page, which is not desired.

Depending on where the float or section is located, it prints a different
string. It behaves differently if a single-sided layout or a double-sided
layout is being used. In a single-sided layout it takes the location on the
*page* into account. In a double-sided layout, however, it operates on the
*double page*. Single pages in a double-sided layout are rather insignificant
in traditional typesetting. The reader is always faced with double pages,
never with single pages.

`\smartref` behaves as follows:

- it prints the reference if it is on the same page (e.g. Figure 1.2)
- it prints the reference and a customizable text if the reference is on the
  next/previous page (e.g. Figure 1.2 on the previous page)
- it prints the reference and the page if the reference is further away than
  one page (e.g. Figure 1.2 on page 42)
