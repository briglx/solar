# Solar Tools
# Emmy and Mike and Brig's Test


Companion tools in researching home solar solutions.

See OneNote docs and README on GitHubs.

## Calculate Solar Angle During Day

This is another line created by Oleg

The website uses the code

```javascript
calcSun(solPosCalc, cityLatLong, cityLatLong.dayAns.selectedIndex, cityLatLong.cities.selectedIndex)
```

# Dev Setup

Setup your dev environment by creating a virtual environment

```bash
# virtualenv \path\to\.venv -p path\to\specific_version_python.exe
# virtualenv .venv /usr/local/bin/python3.10
# python3.10 -m venv .venv
python3 -m venv .venv
source .venv/bin/activate

# Update pip
python -m pip install --upgrade pip

deactivate
```

Install dependencies and link remote path if needed

```bash
pip install -r requirements_dev.txt
```

Configure local.env

```bash
cp local_example.env local.env
# replace  with correct values
```

## Style Guidelines

This project enforces quite strict [PEP8](https://www.python.org/dev/peps/pep-0008/) and [PEP257 (Docstring Conventions)](https://www.python.org/dev/peps/pep-0257/) compliance on all code submitted.

We use [Black](https://github.com/psf/black) for uncompromised code formatting.

Summary of the most relevant points:

- Comments should be full sentences and end with a period.
- [Imports](https://www.python.org/dev/peps/pep-0008/#imports) should be ordered.
- Constants and the content of lists and dictionaries should be in alphabetical order.
- It is advisable to adjust IDE or editor settings to match those requirements.

### Use new style string formatting

Prefer [f-strings](https://docs.python.org/3/reference/lexical_analysis.html#f-strings) over ``%`` or ``str.format``.

```python
#New
f"{some_value} {some_other_value}"
# Old, wrong
"{} {}".format("New", "style")
"%s %s" % ("Old", "style")
```

One exception is for logging which uses the percentage formatting. This is to avoid formatting the log message when it is suppressed.

```python
_LOGGER.info("Can't connect to the webservice %s at %s", string1, string2)
```

### Testing

```bash
pip3 install -r requirements_dev.txt
pip install -r requirements_dev.txt
```

Now that you have all test dependencies installed, you can run linting and tests on the project:

```bash
isort main.py
codespell --skip=".venv,images"
black main.py 
flake8 main.py
pylint main.py
pydocstyle main.py
```



# References

- Noaa Solar Position Calculator https://gml.noaa.gov/grad/solcalc/azel.html
- Install Chrome Web Driver https://chromedriver.chromium.org/getting-started
- Use Webdriver Manager https://stackoverflow.com/questions/64717302/deprecationwarning-executable-path-has-been-deprecated-selenium-python
