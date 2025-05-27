---
title: Understanding GitHub Code Search syntax
shortTitle: Code search syntax
intro: 'You can build search queries for the results you want with specialized code qualifiers, regular expressions, and boolean operations.'
allowTitleToDifferFromFilename: true
versions:
  feature: code-search-upgrade
topics:
  - GitHub search
---

## About code search query structure

The search syntax in this article only applies to searching code with {% data variables.product.prodname_dotcom %} code search. {% data reusables.search.non-code-search-explanation %}

Search queries consist of search terms, comprising text you want to search for, and qualifiers, which narrow down the search.

A bare term with no qualifiers will match either the content of a file or the file's path.

For example, the following query:

```text
http-push
```

The above query will match the file `docs/http-push.txt`, even if it doesn't contain the term `http-push`. It will also match a file called `example.txt` if it contains the term `http-push`.

You can enter multiple terms separated by whitespace to search for documents that satisfy both terms.

For example, the following query:

```text
sparse index
```

The search results would include all documents containing both the terms `sparse` and `index`, in any order. As examples, it would match a file containing `SparseIndexVector`, a file with the phrase `index for sparse trees`, and even a file named `index.txt` that contains the term `sparse`.

Searching for multiple terms separated by whitespace is the equivalent to the search `hello AND world`. Other boolean operations, such as `hello OR world`, are also supported. For more information about boolean operations, see [Using boolean operations](#using-boolean-operations).

Code search also supports searching for an exact string, including whitespace. For more information, see [Query for an exact match](#query-for-an-exact-match).

You can narrow your code search with specialized qualifiers, such as `repo:`, `language:` and `path:`. For more information on the qualifiers you can use in code search, see [Using qualifiers](#using-qualifiers).

You can also use regular expressions in your searches by surrounding the expression in slashes. For more information on using regular expressions, see [Using regular expressions](#using-regular-expressions).

## Query for an exact match

To search for an exact string, including whitespace, you can surround the string in quotes. For example:

```text
"sparse index"
```

You can also use quoted strings in qualifiers, for example:

```text
path:git language:"protocol buffers"
```

## Searching for quotes and backslashes

To search for code containing a quotation mark, you can escape the quotation mark  case insensitivity turned off. For example, to search for the string "True", you w
/?-i)True/
```
