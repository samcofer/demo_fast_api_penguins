# demo-fastapi-penguins

- Code: <https://github.com/SamEdwardes/demo-fastapi-penguins>
- Deployment: <https://colorado.rstudio.com/rsc/demo-fastapi-penguins/docs>

![screenshot](imgs/screenshot.png)

## Usage

Create a virtual environment.

```bash
python -m venv .venv
source .venv/bin/activiate
python -m pip install --upgrade pip wheel
pip install -r app/requirements.txt
```

Then run the app.

```bash
uvicorn app.main:app --reload
```

## Deployment

The app is automatically deployed to RStudio connect using git backed deployment. Make any changes to the code, then run the following:

```bash
rsconnect write-manifest fastapi \
  --overwrite \
  --python .venv/bin/python \
  --entrypoint main:app \
  app
```

> ⚠️ Remember to update the app/requirements.txt file if you add any new packages.