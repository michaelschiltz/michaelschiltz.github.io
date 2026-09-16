---
layout: page
permalink: /publications/
title: Publications
description: Books, articles, chapters, preprints, and reviews. Also on Google Scholar and ORCID.
nav: true
nav_order: 1
---

<!-- _pages/publications.md -->

{% include bib_search.liquid %}

<div class="publications">

<h2 class="category">Books</h2>
{% bibliography --query @book --group_by none %}

<h2 class="category">Working papers and articles under revision</h2>
{% bibliography --query @*[abbr=Preprint] --group_by none %}

<h2 class="category">Journal articles</h2>
{% bibliography --query @article[abbr=Article] --group_by none %}

<h2 class="category">Encyclopedia and handbook entries</h2>
{% bibliography --query @incollection[abbr=Encyclopedia] --group_by none %}

<h2 class="category">Book chapters</h2>
{% bibliography --query @incollection[abbr=Chapter] --group_by none %}

<h2 class="category">Edited volumes, data papers, and teaching resources</h2>
{% bibliography --query @misc[abbr=Edited || abbr=Resource] --group_by none %}

<h2 class="category">Book reviews</h2>
{% bibliography --query @*[abbr=Review] --group_by none %}

</div>
