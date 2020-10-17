# Instructions to use  GOOGLE SCHOLAR scrapper.

## scholarly

scholarly is a module that allows you to retrieve author and publication information from Google Scholar in a friendly way.

## Installation

Use pip to install from pypi:

```
pip3 install scholarly
```
or pip to install from github:

```
pip3 install -U git+https://github.com/OrganicIrradiation/scholarly.git
```
## Usage

Because scholarly does not use an official API, no key is required.

## EXAMPLE

```
from scholarly import scholarly
```
# Retrieve the author's data, fill-in, and print

```
search_query = scholarly.search_author('Steven A Cholewiak')
author = next(search_query).fill()
print(author)
```
# Print the titles of the author's publications

```
print([pub.bib['title'] for pub in author.publications])
```

# Take a closer look at the first publication

```
pub = author.publications[0].fill()
print(pub)
```

# Which papers cited that publication?

```
print([citation.bib['title'] for citation in pub.citedby])
```


### OUTPUT IS IN JSON FORMAT

```
 search_query = scholarly.search_author('Steven A Cholewiak')
 author = next(search_query)
 print(author.fill(sections=['basics', 'indices', 'coauthors']))
```


```
{'affiliation': 'Vision Scientist',
 'citedby': 288,
 'citedby5y': 211,
 'coauthors': [{'affiliation': 'Kurt Koffka Professor of Experimental Psychology, University '
                'of Giessen',
 'filled': False,
 'id': 'ruUKktgAAAAJ',
 'name': 'Roland Fleming'},
               {'affiliation': 'Professor of Vision Science, UC Berkeley',
 'filled': False,
 'id': 'Smr99uEAAAAJ',
 'name': 'Martin Banks'},
               {'affiliation': 'Durham University, Computer Science & Physics',
 'filled': False,
 'id': '3xJXtlwAAAAJ',
 'name': 'Gordon D. Love'},
               {'affiliation': 'Professor of ECE, Purdue University',
 'filled': False,
 'id': 'OiVOAHMAAAAJ',
 'name': 'Hong Z Tan'},
               {'affiliation': 'Deepmind',
 'filled': False,
 'id': 'MnUboHYAAAAJ',
 'name': 'Ari Weinstein'},
               {'affiliation': "Brigham and Women's Hospital/Harvard Medical School",
 'filled': False,
 'id': 'dqokykoAAAAJ',
 'name': 'Chia-Chien Wu'},
               {'affiliation': 'Professor of Psychology and Cognitive Science, Rutgers '
                'University',
 'filled': False,
 'id': 'KoJrMIAAAAAJ',
 'name': 'Jacob Feldman'},
               {'affiliation': 'Research Scientist at Google Research, PhD Student at UC '
                'Berkeley',
 'filled': False,
 'id': 'aYyDsZ0AAAAJ',
 'name': 'Pratul Srinivasan'},
               {'affiliation': 'Formerly: Indiana University, Rutgers University, University '
                'of Pennsylvania',
 'filled': False,
 'id': 'FoVvIK0AAAAJ',
 'name': 'Peter C. Pantelis'},
               {'affiliation': 'Professor in Computer Science, University of California, '
                'Berkeley',
 'filled': False,
 'id': '6H0mhLUAAAAJ',
 'name': 'Ren Ng'},
               {'affiliation': 'Yale University',
 'filled': False,
 'id': 'rNTIQXYAAAAJ',
 'name': 'Steven W Zucker'},
               {'affiliation': 'Brown University',
 'filled': False,
 'id': 'JPZWLKQAAAAJ',
 'name': 'Ben Kunsberg'},
               {'affiliation': 'Rutgers University, New Brunswick, NJ',
 'filled': False,
 'id': '9XRvM88AAAAJ',
 'name': 'Manish Singh'},
               {'affiliation': 'Kent State University',
 'filled': False,
 'id': 'itUoRvUAAAAJ',
 'name': 'Kwangtaek Kim'},
               {'affiliation': 'Silicon Valley Professor of ECE, Purdue University',
 'filled': False,
 'id': 'fD3JviYAAAAJ',
 'name': 'David S. Ebert'},
               {'affiliation': 'MIT',
 'filled': False,
 'id': 'rRJ9wTJMUB8C',
 'name': 'Joshua B. Tenenbaum'},
               {'affiliation': 'Chief Scientist, isee AI',
 'filled': False,
 'id': 'bTdT7hAAAAAJ',
 'name': 'Chris Baker'},
               {'affiliation': 'Professor of Psychology, Ewha Womans University',
 'filled': False,
 'id': 'KXQb7CAAAAAJ',
 'name': 'Sung-Ho Kim'},
               {'affiliation': 'Assistant Professor, Boston University',
 'filled': False,
 'id': 'NN4GKo8AAAAJ',
 'name': 'Melissa M. Kibbe'},
               {'affiliation': 'Nvidia Corporation',
 'filled': False,
 'id': 'nHx9IgYAAAAJ',
 'name': 'Peter Shirley'}],
 'email': '@berkeley.edu',
 'filled': False,
 'hindex': 8,
 'hindex5y': 8,
 'i10index': 8,
 'i10index5y': 7,
 'id': '4bahYMkAAAAJ',
 'interests': ['Depth Cues',
               '3D Shape',
               'Shape from Texture & Shading',
               'Naive Physics',
               'Haptics'],
 'name': 'Steven A. Cholewiak, PhD',
 'url_picture': 'https://scholar.google.com/citations?view_op=medium_photo&user=4bahYMkAAAAJ'}
```
