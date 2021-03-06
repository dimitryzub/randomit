# Randomit 🎲

A Python library to generate random things.

[![codecov coverage](https://codecov.io/gh/dimitryzub/randomit/branch/main/graph/badge.svg?token=B2XA8Y3R5M)](https://codecov.io/gh/dimitryzub/randomit)
![example workflow](https://github.com/dimitryzub/randomit/actions/workflows/ci.yml/badge.svg)

![pypi package badge brought by Gemfury](https://badge.fury.io/py/randomit.svg)
[![Downloads](https://static.pepy.tech/personalized-badge/randomit?period=month&units=international_system&left_color=grey&right_color=brightgreen&left_text=Downloads)](https://pepy.tech/project/randomit)

![pypi package versions brought by shields.io](https://img.shields.io/pypi/pyversions/randomit)
![licence brought by shields.io](https://img.shields.io/github/license/dimitryzub/randomit?color=blue)
![repo size](https://img.shields.io/github/repo-size/dimitryzub/randomit)

![twitter account brought by shield.io](https://img.shields.io/twitter/follow/DimitryZub?style=social)
___
Currently, `randomit` can:
- Generate [random word(s)](https://github.com/dimitryzub/randomit#get-random-words) based on a given [theme](https://github.com/dimitryzub/randomit#look-for-available-built-in-themes).
- [Load your files](https://github.com/dimitryzub/randomit#load-and-pass-file-with-words) that _contain **words**_ to randomize them. 
- [Randomize images](https://github.com/dimitryzub/randomit#get-random-images) based on a given query.
- Generate random [phone numbers](https://dimitryzub.github.io/randomit/docs/docs.html#get-phone-number).
- Generate/randomize [email address](https://dimitryzub.github.io/randomit/docs/docs.html#get-email-address). 

To see what's coming next, see [open projects](https://github.com/dimitryzub/randomit/projects).

## 💡Usage

> *Words/addresses will always be different on each execution no matter what arguments being passed.*

### Get Random Words

```python
from randomit.randomizer import Words

# return one word
Words(theme='random words').randomize(return_one_word=True)
# cabinet
# bristlecone pine
# dim - bright

Words(theme='random words').randomize()  # returns a list of 17k words
Words(theme='random words').randomize(amount_to_return=3)  # ['axis', 'overabundant', 'superuser']

Words(theme='random words').randomize(letter_starts_with='A')  # returns all words that starts with letter "A" 
Words(theme='random words').randomize(letter_starts_with='A', amount_to_return=3)  # ['abandoned', 'able', 'absolute']
Words(theme='names').randomize(letter_starts_with='A', amount_to_return=3, capitalize=True)  # ['Apron', 'Ashes', 'Anvil']
```

### Get Random Addresses

```python
import json

address_list = Words(theme='address').randomize(amount_to_return=1, return_dict=True)

print(json.dumps(address_list, indent=2))

'''
[
  {
    "address": "279 troy road",
    "city": "east greenbush",
    "state": "ny",
    "zip": "12061"
  }
]
'''

# if "return_dict" argument isn't specified it will return a list():
'''
["2465 hempstead turnpike, east meadow ny 11554"]
'''
```

_If you want to add your list of addresses, have a look at `addresses_list.txt` and format it as it's formatted there to work properly._

Format:`address, city, state, zip`

### Look for available built-in themes

_If "**theme**" argument is not specified ➡ defaults to "**random words**"_.

```python
Words().available_themes()
# ['random words', 'names', 'surnames', 'cities', 'countries', 'address']
```

### Specify theme you want to get words from

```python
Words(theme='cities').randomize()  # pass available arguments
```

### Load and pass file with words
_Make sure all words are **lowercase**, and start on a **new line** (`\n`), otherwise it won't work._

```python
# call your words
Words(file=YOUR_FILE).randomize(capitalize=True, return_one_word=True)

# Bazinga!
```

___

### Get Random Images

_Enter any query, and it will return a random image(s) URL based on the provided query, and it will be random on each execution._ 



```python
from randomit.randomizer import Images

Images(query='cats', amount_to_return=3).get_randomized() 
# ['https://images.pexels.com/photos/1170986/pexels-photo-1170986.jpeg', 'https://images.pexels.com/photos/1056251/pexels-photo-1056251.jpeg', 'https://images.pexels.com/photos/1056251/pexels-photo-1056251.jpeg']

# if "amount_to_return" argument is not specified -> defaults to batch of 100 images.
```

> Note: If you don't need this feature and want to get rid of dependencies, [use `poetry remove package_name`](https://python-poetry.org/docs/cli/#remove)

In this case:

```lang-none
poetry remove lxml
poetry remove requests
poetry remove bs4
```

___

## 📡 Installation

```
pip install randomit
```

```
git clone https://github.com/dimitryzub/randomit.git
```

## 👾 Suggestions

If you have any suggestions or ideas what will be good to add, get involved in [discussions](https://github.com/dimitryzub/randomit/discussions) section.

## 🔬 Issues

For issues, visit [issues page](https://github.com/dimitryzub/randomit/issues) 🙃

Note for [replit.com](https://replit.com/) users. If you’re using `randomit` on replit, it will throw an error for no obvious for me reason. If you know how to fix it, please, let me know. 

Installing package locally via `pip` doesn’t produce such error as it should (_tested in Pycharm and VSCode_).

## 📜 Docs

To read more in-depth about something, visit [documentation](https://dimitryzub.github.io/randomit/docs/docs.html) page. Currently, there's nothing there. It's under development. Soon there will be more examples. 