---
title: PopGen Genepop
permalink: wiki/PopGen_Genepop
layout: wiki
---

Genepop support
===============

Genepop support is actually 2 things: The support for the file format,
the de facto standard in frequency analysis in population genetics and
the support for the application itself.

File format
-----------

The current implementation of the parser reads the whole file to a
memory structure. This might not be acceptable for very big files with
thousands of individuals and thousands of loci. An iterator version is
under construction.

The parser is strict regarding the format (i.e., the individual
identifier is expected to terminate in a comma). Some applications are
less strict, but there is no intention for now to support a relaxed
version of the specification.

According to the specification, the last individual of each population
is also the subpopulation identifier. This is not great design and in
reality users many times forget this. As such the expectation that the
last individual id is the subpopulation id many times does not happen.

Application support
-------------------

Two interfaces are supplied: A general, more complex and more efficient
one (GenePopController) and a simplified, more easy to use, not complete
and not so efficient version (EasyController)