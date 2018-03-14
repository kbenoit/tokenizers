---
title: "Fast, Consistent Tokenization of Natural Language Text"
tags:
- text mining
- tokenization
- natural language processing
authors:
- name: Lincoln A. Mullen
  orcid: 0000-0001-5103-6917
  affiliation: 1
- name: Kenneth Benoit
  orcid: 0000-0002-0797-564X
  affiliation: 2
affiliations: 
- name: "Department of History and Art History, George Mason University"
  index: 1
- name: London School of Economics and Political Science
  index: 2
date: 12 March 2018
bibliography: paper.bib
...

Computational text analysis usually proceeds according to a series of well
defined steps. After importing text data, the usual next step is to turn the
human-readable text into machine readable tokens. Tokens are defined as segments
of a text identified as meaningful units for the purpose of analyzing the text,
and usually consist of individual terms, but may also consist of larger or
smaller segments, such as paragraphs, sentences, lines, word sequences, or word
subsequences.  [@Manningetal2008, 22] Tokenization is the process of splitting
the text into these smaller pieces, and often preprocessing the text to remove
punctuation and transform all tokens into lowercase. [@welbers_text_2017]
Decisions made during tokenization have a significant effect on subsequent
analysis. [@denny_text_forthcoming] Especially for large corpora, tokenization
can be computationally expensive.

The [tokenizers package](https://ropensci.github.io/tokenizers/) for R
([GitHub](https://github.com/ropensci/tokenizers), [Zenodo](ZENODO LINK TK))
provides fast, consistent tokenization for natural language text. [@rbase] Each
of the tokenizers expects a consistent input and returns a consistent output, so
that the tokenizers can be used interchangeably with one another or relied on in
other packages. To ensure the correctness of output, the package depends on the
**stringi** package, which implements Unicode support for R. [@gagolewski_2018]
To ensure the speed of tokenization, key components such as the _n_-gram and
skip _n_-gram tokenizers are written using the **Rcpp** package.
[@eddelbuettel_2013, @eddelbuettel_2017] The **tokenizers** package is part of
the [rOpenSci project](https://ropensci.org/).

The most important tokenizers in the current version of the package can be grouped as follows:

- tokenizers for characters and shingled characters
- tokenizers for words and word stems, as well as for Penn Treebank tokens 
- tokenizers n-grams and skip n-grams
- tokenizers for Tweets, which preserve formatting of usernames and hashtags

In addition the package provides functions for splitting longer documents into sentences and paragraphs, or for splitting a long text into smaller chunks each with the same number of words. The package also provides functions for counting words, characters, and sentences.

The tokenizers in this package can be used on their own, or they can be wrapped by higher-level R packages. For instance, the **tokenizers** package is a dependency for the **tidytext** [@silge_2016], **text2vec** [@selivanov_2018], and **textreuse** [@mullen_2016] packages. More broadly, the output of the tokenization functions follows the guidelines set by the text-interchange format  defined at an rOpenSci Text Workshop in 2017. [@tif_2017] Other packages which buy into the text-interchange format can thus use the ***tokenizers** package interchangeably.

The **tokenizers** package has research applications in any discipline which uses computational text analysis. The package was originally created for the author's historical research into the use of the Bible in American newspapers [@mullen_americas] and into the borrowing of legal codes of civil procedure in the nineteenth century United States [@funkmullen_spine_2018, @funkmullen_servile_2016]. The `tokenizers` package underlies the **tidytext** package [@silge_text_2017], and via that package **tokenizers** has been used in disciplines such as political science [@sanger_2015_], social science [@warin_mapping], communication studies [@xu_using_2018], English [@ballier_rbased_2017], and the digital humanities more generally.

# References
