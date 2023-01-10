PROBLEM STATEMENT:

Building a search engine for Environmental News NLP Archive and perform the comparison of metrics with available search engines.

* DESCRIPTION

The aim is to implement a search engine that answers the queries on Environmental News NLP Archive. In the first part, the corpus is created, by indexing the documents and snippets and secondly the search queries are answered using the index created. To which features like, spell-check, ranking are added. To grade the implementation, similarity checks with the existing search engine- Elastic search.

* Dataset

Environmental News NLP Archive : Contains 418 documents fromvarious news stations containing the news article URL, Match DateTime, station, source, IAshowId, IA preview Thumb, snippet.

* Inverted Index

Inverted Index is a data structure that is built to parse the documents that the queries are answered on. Given a query, the index is used to return the list of documents and snippets relevant for the query. The inverted index contains mappings from terms to the documents that those terms appear in. Wherein, each term is a key in the index whose value is its postings list. A posting list of a term is the list of documents that the term appears in.

* Query Types

The search engine implemented answers the query types namely:

1. One-word Queries: Queries that consist of a single word.

2. Free test Queries: Queries that consist of sequences of words separated by space, where the result will be the implicit logical ‘OR’ of all the terms present in the query.

3. Phrase Queries: Queries that again consist of sequences of words separated by space, and inserted with the double quotes so that the documents to contain the terms in the query exactly in the specified order are to be fetched.

4. Wild-card Queries: Queries that are uncertain about the spelling of a term or when multiple spelling variants of a term exist.

5. Proximity Queries: Queries that require the term in the query to be occurring in the given proximity within a snippet.

* Spell Check

If the query word exists in the vocabulary then we assume that it is correct. If this word does not exist in the vocabulary we try to find the most similar words.The similar words are sorted based on Jaccard Distance by computing the 2Q grams of the words and returned the 3 most similar words order by Similarity and Probability.

COMPARISON

We compare all queries types of our IR systems with elastic searchengine and following are the response time:


Query             |Our IR System    | Elastic Search

Free Text Query   |0.01 secs        | 0.063 secs
Wildcard Query    |0.87 secs        | 0.052 secs
Proximity Query   |0.0014 secs      | NA
Phrase Query      |0.012 secs       | NA


INTERPRETATION OF EFFICIENCY

We have calculated the Precision and Recall of 5 queries for our IR system by measuring it against the elastic search results considering it
as relevant documents. For Free Text query Precision is 0.97 and Recall is 1. This means our IR system is retrieving all the relevant documents from the database
plus a few false positives.

LEARNING OUTCOME
● Building IR systems for query searching.
● Building Posting listing and Dictionary using B-Trees
● Handling Different types of Queries
● Building Spelling Correction using Jaccard Coefficient
● Hands on of ElasticSearch
