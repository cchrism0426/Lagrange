---
layout: page
title: Search
---

<style>
  #search-container {
    max-width: 100%;
  }

  input[type=text] {
    font-size: normal;
    outline: none;
    padding: 1rem;
    background: rgb(236, 237, 238);
    width: 100%;
    -webkit-appearance: none;
    font-family: inherit;
    font-size: 100%;
    border: none;
    border-radius: 5px;
    box-sizing: border-box;
  }

  #results-container {
    margin: .5rem 0;
    padding: 0;
    list-style: none;
  }

  #results-container a {
    text-decoration: none;
  }
</style>

<!-- Html Elements for Search -->
<div id="search-container">
<input type="text" id="search-input" placeholder="Search posts...">
<ul id="results-container"></ul>
</div>

<!-- Script pointing to search-script.js -->
<script src="/search.js" type="text/javascript"></script>

<!-- Configuration -->
<script type="text/javascript">
SimpleJekyllSearch({
  searchInput: document.getElementById('search-input'),
  resultsContainer: document.getElementById('results-container'),
  json: '/search.json',
  searchResultTemplate: '<li><h3><a href="{url}">{title}</a></h3></li>',
  noResultsText: 'No results found',
  limit: 10
})
</script>