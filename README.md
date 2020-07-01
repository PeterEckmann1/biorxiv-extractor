<h1>biorxiv-extractor</h1>
Extracts data from medRxiv and bioRxiv preprints.

<h2>Usage</h2>

```
python biorxiv.py [-h] [--noheader] [--section {methods,results,discussion}] doi {pdf,json,txt} outfile
```

 * `doi` is the DOI of the preprint to extract.
 * `format` must be either `pdf`, `json`, or `txt`, and specifies the file format to download the preprint in.
   * `pdf` downloads the preprint in its raw PDF format
   * `json` uses full-text HTML if available, otherwise an error is thrown. 
     The main sections of the paper are labeled in a `json` list, and all subheaders are removed.
   * `txt` uses full-text HTML if available, otherwise an error is thrown. Using `txt` will by default extract the paper's entire text, excluding references.
     A specific section can be specified using `--section`, i.e. `--section=methods`, `--section=results`, or `--section=discussion`. All headings and subheadings will be included in the `txt` by default, but can be disabled using `--noheader`
     
 * `outfile` is where the result is saved.


<h2>Setup</h2>
Python 3.6.0 or greater is required for the json option to work correctly, but any version of Python 3 will work for pdf and txt extraction.
<h3>Dependencies</h3>

 * [`beautifulsoup4 >= 4.9.1`](https://pypi.org/project/beautifulsoup4/), install with `pip install beautifulsoup4`
 * [`requests >= 2.22.0`](https://pypi.org/project/requests/), install with `pip install requests`
