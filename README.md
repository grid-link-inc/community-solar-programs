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

Refresh poetry lock file as per https://python-poetry.org/docs/basic-usage/#as-a-library-developer
```bash
poetry update
```

Run tests

```bash
poetry build
```
