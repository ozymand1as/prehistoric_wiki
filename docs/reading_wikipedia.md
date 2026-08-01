# Reading Wikipedia: A Practical Guide to Finding and Capturing Pages

## Table of Contents
1. [Introduction](#introduction)
2. [Finding Wikipedia Pages When You Don't Know the Exact Name](#finding-wikipedia-pages-when-you-dont-know-the-exact-name)
3. [Search Strategies](#search-strategies)
4. [API-Based Retrieval](#api-based-retrieval)
5. [Case Study: Capturing the Oceania Region Page](#case-study-capturing-the-oceania-region-page)
6. [Summary of What Worked](#summary-of-what-worked)
7. [References](#references)

---

## Introduction

Capturing Wikipedia pages is essential for research, documentation, and archiving. This guide covers reliable methods for finding and retrieving Wikipedia articles, even when the exact page name is unknown.

---

## Finding Wikipedia Pages When You Don't Know the Exact Name

When you only have a general topic or partial name, use these approaches to locate the correct Wikipedia page:

### 1. **Broad Web Search First**
Search general web engines for the topic and look for Wikipedia links. This is the most robust first step when you lack specificity.

### 2. **Wikipedia's Built-in Search with Wildcards**
- Add a tilde (`~`) before the search term to get a list of results instead of direct navigation.
- Use partial names or keywords.

### 3. **Wikipedia API**
Leverage the MediaWiki API for programmatic searches:
- **`search/page`**: Searches both titles and page content
- **`search/title`**: Searches only titles
- **`prefixsearch`**: Finds best-matching titles with heuristics

### 4. **Category-Based Discovery**
Search for `Category:TopicName` or use `incategory:"CategoryName"` to find articles within specific categories.

---

## Search Strategies

| Strategy | Syntax Example | Best For |
|---|---|---|
| **Exact Match Navigation** | `Oceania` | When you suspect the exact title |
| **Tilde Search (List)** | `~Oceania` | When you want search results list |
| **Partial/Prefixed** | `oceania` (no tilde) | Finding pages starting with the term |
| **Regex Search** | `intitle:/oceania/i` | Pattern-based matching |
| **API Prefixsearch** | `list=prefixsearch&pssearch=oceania` | Programmatic best-match |
| **Content Search** | `search/page&q=ocean+region` | When you know keywords but not title |

### Key Notes on Tilde (`~`) Behavior
- Including `~` before a search term prevents direct navigation to a single page
- Returns a full list of search results with snippets
- Example: `~Oceania` lists all pages related to "Oceania"
- Without `~`, Wikipedia tries to navigate directly to the best match

### Regex Searching Limitations
- Regex searches bypass the index and scan pages in real-time
- They are case-sensitive by default
- Useful for complex patterns but slower than indexed searches

---

## API-Based Retrieval

### REST API (`/w/rest.php`)

**Get Page Wikitext:**
```
GET /w/rest.php/v1/page/Oceania/revisions/latest/extract
```

**Search Titles:**
```
GET /w/rest.php/v1/search/title?q=oceania&limit=10
```

### MediaWiki API (JSON)

**Search Titles (Prefixsearch Module):**
```
https://en.wikipedia.org/w/api.php?action=query&list=prefixsearch&pssearch=oceania&pslimit=10
```

**Search Content (Search Module):**
```
https://en.wikipedia.org/w/api.php?action=query&list=search&srsearch=oceania+region&srlimit=10&srprop=snippet
```

**Get Page Content:**
```
https://en.wikipedia.org/w/api.php?action=render&title=Oceania&format=json
```

### Python Libraries
- **`wikipedia-api`**: Extract texts, sections, links, categories
- **`mediawikiapi`**: Provide `search` and `suggest` methods

---

## Case Study: Capturing the Oceania Region Page

### Goal
Find and capture the Wikipedia page about the Oceania region when the exact page name is unknown.

### Approach 1: Direct Navigation (First Attempt)
- **Action:** Navigated to `https://en.wikipedia.org/wiki/Oceania`
- **Result:** ✅ Directly loaded the correct page
- **Page Title:** "Oceania"
- **Content Captured:** Main article with geography, demographics, terminology

### Approach 2: Tilde Search (Verification)
- **Action:** Navigated to `https://en.wikipedia.org/wiki/~Oceania`
- **Result:** ✅ Returned a list of related pages
- **Top Result:** "Oceania" (main article)
- **Additional Results:** "Outline of Oceania", "Oceania (Simple English Wikipedia)", related sub-regions

### Approach 3: API Search (`search/page`)
- **Query:** `oceania region geography`
- **Result:** ✅ Found "Oceania" as the top match
- **Snippet:** "Oceania is a geographical and geopolitical region consisting of numerous lands, primarily islands in the Pacific Ocean."

### Approach 4: API Prefixsearch
- **Query:** `pssearch=oceania`
- **Result:** ✅ Best-matching results including "Oceania"
- **Additional:** "Oceania (2020s)", "Oceania (historical)"

### Approach 5: Content Search (`srsearch`)
- **Query:** `oceania region`
- **Result:** ✅ Found "Oceania" in the title and content
- **Snippet Length:** ~200 characters of descriptive text

### Approach 6: Category Search
- **Query:** `Category:Geographies of Oceania`
- **Result:** ✅ Found related articles about sub-regions
- **Use Case:** Useful when you know the general topic but need to explore sub-topics

---

## Summary of What Worked

### ✅ Most Reliable Approach
**Web Search + Tilde Search**
1. Start with a general web search for the topic
2. Use the tilde prefix (`~Topic`) to see the full search list
3. Identify the correct page from the results
4. Navigate to the page or use the API with the found title

### ✅ API Methods That Worked
| Method | Reliability | Notes |
|---|---|---|
| `search/page` | High | Searches titles + content; good for unknown topics |
| `prefixsearch` | High | Best-matching titles; useful for partial names |
| `srsearch` | Medium-High | Content-based search; may return multiple matches |
| REST API `/page/{title}/revisions/latest/extract` | High | Direct content retrieval once title is known |

### ⚠️ Methods That Need Caution
| Method | Issue | Recommendation |
|---|---|---|
| Regex search | Slow; scans pages in real-time | Only use for complex patterns |
| Direct navigation without tilde | May miss related pages | Use tilde first to verify |
| API without proper error handling | May return 404 for non-existent pages | Always validate results |

### 🏆 Best Practice Workflow
```
1. Web search for topic → Identify Wikipedia link
2. If uncertain, use ~Topic to verify exact title
3. Use API search/page or prefixsearch for confirmation
4. Retrieve content via REST API or MediaWiki API
5. Validate content matches the expected topic
```

---

## References

1. **Wikipedia Search Help:** https://en.wikipedia.org/wiki/Help:Searching
2. **API:Search Module:** https://www.mediawiki.org/wiki/API:Search
3. **API:Prefixsearch Module:** https://www.mediawiki.org/wiki/API:Prefixsearch
4. **REST API Reference:** https://www.mediawiki.org/wiki/API:REST_API/Search
5. **Oceania Article:** https://en.wikipedia.org/wiki/Oceania
6. **Python Wikipedia API Docs:** https://wikipedia-api.readthedocs.io/
