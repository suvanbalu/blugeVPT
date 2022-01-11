# Search Functionality using BLUGE

<img src="https://blugelabs.com/img/avatar.png" alt="bluge-icon" width="200" align="right"/>

## What is Bluge?
Bluge is an indexing/search library for Go.Developers can then search the index to find matching documents. Bluge supports many types of queries, which can be composed into more complex queries with boolean operators.Bluge supports an advanced aggregation framework, allowing the developer to compute aggregated values over the set of matching documents.It uses **bleve** search and **BM25 algorithm** for searching and indexing. 

### What is a search functionality?

Users can quickly find information on a website using a search index. It is designed to map search queries to documents or URLs that might appear in the results.
When a user types in a search query, the search engine will find documents that include the search query. The results are returned from the index with a title, short content highlight, possibly a picture and a reference to the page URL.

### How are search-index made?
The search index for websites is created by crawlers – also known as web crawlers and web spiders. In simple terms, the crawler visits the pages of the website and collects the contents from the website. This data is then converted into an index.

### How are data searched from index?
Once the user enter their keyword , the program searches for the keyword in all indexes and once the matching index is found and the results are returned from the index with a title, short content highlight, possibly a picture and a reference to the page URL.

### How a search-index can improve your website?
Search engines collect the content of your website automatically. Through an algorithm, your search results are prioritized. Some results will be given more weight, so they will show up before other pages on the results page.

### Why bluge over bleve?
The design of Bluge is largely the same as Bleve. One of the biggest design changes of Bluge is that it now supports a **pluggable Directory** implementation. This Directory interface decouples the index implementation from many OS/filesystem details. This let us introduce a much more **efficient in-memory-only index**, something Bleve still struggles to offer today.

The next major change is that Bluge supports accessing the index from **multiple process** (via OS locking primitives). Only one process can write at a time, but it is very useful architecturally to be able to search indexes from multiple processes, which is not possible with Bleve today.

Finally, there are a bunch of other smaller changes. Bluge uses **BM25**, not TF/IDF, and has **more configurable/customizable scoring**. And Bluge has a **proper aggregation framework**, allowing you to easily build your own aggregations over all the search hits seen (in Bleve, only a limited faceting option is available).