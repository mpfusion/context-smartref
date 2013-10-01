### Smart References

This ConTeXt module simplifies and automates references to floats or sections.
It has the same semantics as `\in` and takes the same arguments. At the moment
it provides the single command `\smartref`, which is basically `\in`, `\at`
and `\atpage` merged together into one single command. Here is an example:

    \smartref{figure}[fig:somefigure]

The existing commands are not flexible enough. `\atpage` does not have the
concept of double pages. This means it might, for instance, print ”as we show
above” even if the float is visible. `\somewhere` doesn't suppress the
reference text if the reference happens to end up on the same page, which is
not desired. Furthermore, the user needs to remember to use `\in` if the
sections should be referred to by number. If on the other hand, a reference
should be referred to by title the command `\about` is used. The `\smartref`
command automatically refers to the section by number if it is available. If
the user turns off numbering, the sections are referred to by title.

Depending on where the floats or sections are located, `\smartref` prints
a different string. It behaves differently if a single-sided layout or
a double-sided layout is being used. In a single-sided layout it takes the
location on the *page* into account. In a double-sided layout, however, it
operates on the *double page*. Single pages in a double-sided layout are
rather insignificant in traditional typesetting. The reader is always faced
with double pages, never with single pages.

`\smartref` behaves as follows:

- it prints the reference if it is on the same page (e.g. Figure 1.2)
- it prints the reference and a customizable text if the reference is on the
  next/previous page (e.g. Figure 1.2 on the previous page)
- it prints the reference and the page if the reference is further away than
  one page (e.g. Figure 1.2 on page 42)
