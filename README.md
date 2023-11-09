# **Django Starter Project**

[![Python](https://img.shields.io/badge/python-3.10-4584b6?labelColor=ffde57&logo=python)](https://www.python.org/downloads/release/python-3100/) ![Django](https://img.shields.io/badge/django-4.2-white?labelColor=092e20&logo=django)
[![Black](https://img.shields.io/badge/code%20style-black%20--%20v23.11.0-black?labelColor=white)](https://github.com/psf/black) [![Code Linting](https://img.shields.io/badge/linting-flake8-orange.svg?labelColor=white)](https://github.com/PyCQA/flake8) [![Git Hooks](https://img.shields.io/badge/git--hooks-pre--commit-green.svg?labelColor=white)](https://pre-commit.com)

## Running the Project (Local)

- [ ] Get a copy of the `local_settings` from one of the developers.
- [ ] Run database separately, either a docker container or a system service. It's not included as part of the project setup.
- [ ] Change `DATABASES` in the local_settings file to connect to your database.
- [ ] Create a python virtual env - `python3 -m venv venv`
- [ ] Activate the environment - `source venv/bin/activate`
- [ ] Install dependencies - `pip install -r requirements.txt`
- [ ] Run - `pre-commit install` to enable pre-commit git hooks
- [ ] Run migrations - `python manage.py migrate`
- [ ] Run server - `python manage.py runserver`

## Project Structure

There are following main directories:

**1. apps.** Contains all the apps of this project. All the configuration has been changed to identify the apps under this directory. To create an app, first create the directory inside `apps`, then run `django-admin startapp <app_name> apps/<app_name>`.

```bash
# From the root directory
> mkdir apps/<app_name>
> django-admin startapp <app_name> apps/<app_name>
```

**2. apiserver.** Contains all the configuration and settings.

### `apps`

The code snippet in `settings.py` and present below ensures that the `apps` directory is treated as the parent of all the apps.

```python
# Use apps directory as parent of all the apps
sys.path.insert(0, os.path.join(BASE_DIR, "apps"))
```

### `apiserver`

All the configurations for the project are to be stored here. The current structure has the following configurations.

1. `wsgi.py` -  Sync server config
2. `asgi.py` - Async server config
3. `urls.py` - Root URL config
4. `settings/` - This directory contains all django and application related settings


## Contact List

- [ ] Amal Salvin Joseph - amalsalvin97@gmail.com

___


## Development Checklist

- [ ] You are not repeating the code, follow DRY (**D**o not **R**epeat **Y**ourself)
- [ ] Add logs as much possible. Use the configured logger to do the same with appropriate log level. Examples:

  ```python
  """ My module """
  import logging
  logger = logging.getLogger(__name__)

  logger.info("My awesome message with %s", variable)
  logger.error("Some weird error %s", err_msg)
  logger.debug("I can show detailed debug-agnostic logs")
  ```

- [ ] Add comments when you know that re-visiting particular snippet will need help and needs explanation.
- [ ] Make sure that you install `black` as the formatter in your editor.
 - Refer [this](https://gist.github.com/camsvn/fc48f483004c718e49d20d29b34823a2) document to configure black in you editor
- [ ] Git guidelines: Use [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
