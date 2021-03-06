scholar
========

Retrieve article information from Google Scholar in Python

Features
--------

- Extracts the following information for each article:
    - title
    - authors
    - year
    - citation count
    - number of online versions
    - URL to PDF
    - URL to Journal entry
    - URL to citing articles
    - URL to versions
- Format results in json, pickle, or nested dicts
- FieldSets provide an easy way to update the scraper as the Scholar html layout changes
- Integrity tests to verify whether the parser is working, or identify which fields are no longer being parsed correctly
- Command line interface to extract articles directly to terminal/file

Scholar is influenced heavily by [scholar.py](https://github.com/ckreibich/scholar.py) from Christian Kreibich, and includes a number of the patches which were incorporated into that project.

Scholar has been tested with Python 2.7 and 3.3.

Example
-------

From the command line:

```bash
scholar.py --max_results 1
           --encoding json
           --file articles.json
           --author Marr
           Theory of edge detection
```

From within a Python project:

```python
import scholar as gs
articles = gs.query(search='Theory of edge detection',
                    author='Marr',
                    max_results=1)

print(articles[0].dumps('json'))
```

WARNING!
--------
Google's Terms of Service strictly prohibit scraping any Google content, including Google Scholar. Using this package is in direct violation of their Terms of Service. You use it at your own risk, and bear any consequences Google imposes upon you.

If you DO decide to use this module, please be aware that scraping Google Scholar consumes Google bandwidth and resources, and doesn't provide revenue or compensation. If you run this scraper automatically, consider limiting the number of requests per day.
