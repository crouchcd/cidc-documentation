## Unit Testing with Pytest

#### Install

Install the following python packages in your project:

`pipenv install pytest, pytest-cov, pytest-html --dev`


#### Project structure:

```
Root-folder/
  project-name/
    application-code/
    tests/
      conftest.py
      tests.py
```

#### conftest.py
This python file is used to tell pytest how to structure the path so that imports in tests actually work:

```
"""
Configuration file for pytest.
"""
import sys
from os.path import abspath, dirname
PACKAGE_PATH = abspath(dirname(dirname(__file__)))
sys.path.insert(0, PACKAGE_PATH)
```

#### Running tests locally

First activate the venv: `pipenv shell`

To generate the coverage.xml: `py.test my-application --cov-report xml:coverage.xml --cov my-application`

To generate the html report: `pytest --htlm=report.hml`

