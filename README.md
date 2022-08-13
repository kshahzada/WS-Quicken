
# NOTEBOOK-TEMPLATE

 Where the magic happens (easier).

## Dependancies

- Docker
- VS Code
- VS Code Extension: Python, Jupyter (Optional - if you want to edit directly in VS Code)
- Pre-Commit (`brew install pre-commit`)

## Getting Started

1. Get to the right project - Navigate to this repo in the terminal
2. Start up the Jupyter Server - Enter `docker-compose up`
3. Start doing stuff - Either use the built in Jupyter plug-in for VS Code and work directly in VS Code, or copy the URL from the output of the `docker-compose up` command to a browser

You can also click `open in container` within VSCode now

## Hot Tips

- Don't save PII to the cloud (names, emails, social insurance numbers, etc) - if you need to work with them locally
- If you need a library not installed on the base image ([check here](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#jupyter-scipy-notebook)) then add `!pip install {package you want}` into the notebook; don't mess around with the `docker-compose.yaml` file
- The paths and what directory is running the notebook can sometimes get wonky, so if a data file isn't loading correctly, that is often the culprit; the path to the root of this directory is `/home/jovyan/work`
- If you want to save secret keys locally (DO NOT COMMIT SECRET KEYS) you can add `*.creds.*` to ignore a file in the repo

```python
# just save a json file with the secret locally
secrets = {}
with open(***file path***) as json_file:
    secrets = json.load(json_file)
```
