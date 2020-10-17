# Instructions to use  GOOGLE SCHOLAR scrapper.

## scholarly

scholarly is a module that allows you to retrieve author and publication information from Google Scholar in a friendly way.

## Installation

Use pip to install from pypi:
```
pip3 install scholarly
```
or pip to install from github:

```pip3 install -U git+https://github.com/OrganicIrradiation/scholarly.git
```
## Usage

Because scholarly does not use an official API, no key is required.

## EXAMPLE

```
from scholarly import scholarly
```
# Retrieve the author's data, fill-in, and print

```search_query = scholarly.search_author('Steven A Cholewiak')
author = next(search_query).fill()
print(author)
```
# Print the titles of the author's publications

```print([pub.bib['title'] for pub in author.publications])
```

# Take a closer look at the first publication

```pub = author.publications[0].fill()
print(pub)
```

# Which papers cited that publication?

```print([citation.bib['title'] for citation in pub.citedby])
```

