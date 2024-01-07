https://pypi.org/project/communitysolarprograms/

# Community Solar Programs

Community Solar Programs represented as code.

Understanding potential earnings from community solar programs is difficult. This library attempts to make it easy by encoding program compensation structures (defined in regulatory, policy, and other legislative documents) as runnable code.

# Installation

```bash
pip install communitysolarprograms
```

# Usage

```python
import communitysolarprograms

earnings = communitysolarprograms.massachusetts.calculate_potential_earnings()
```

# Developing 

```bash
poetry shell
poetry install
```

## As a dependency to another project

Install this package in editable mode. This command will install the package locally in such a way that changes to the package's source code will be immediately reflected in the environment where it's installed.
```bash
pip install -e .
```
Navigate to the other project
```bash
cd ../path/to/other/project/
```

Set this project as a local dependency:

Poetry:
```bash
poetry add /path/to/communitysolarprograms
```

XOR setup.py
```py
setup(
    name="other_package",
    ...
    install_requires=[
        "communitysolarprograms @ file:///absolute/path/to/communitysolarprograms"
    ]
)
```

Install it
```bash
pip install -e .
```


# Publishing

## One-time setup
```bash
pip install twine
```

Create API tokens for your PyPI and TestPyPI accounts, then write them to new config file using the script below:

```bash
content="[pypi]
username = __token__
password = <PyPI token>
[testpypi]
username = __token__
password = <TestPyPI token>"

echo "$content" > $HOME/.pypirc
```

[More details here](https://packaging.python.org/en/latest/specifications/pypirc/#using-a-pypi-token).

## Build
```bash
poetry update # to keep dependencies recent. 
# Run tests
poetry build
```

## Test Publish
```bash
twine upload --repository testpypi dist/* 
pip install -i https://test.pypi.org/simple/ communitysolarprograms
python 
import community_solar_programs
```

## Publish
```bash
twine upload dist/* 
```