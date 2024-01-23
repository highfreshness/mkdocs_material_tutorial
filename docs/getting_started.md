# Material for MKDocs gettting started

Learn how to create and host a documentation site using Material for MkDocs on GitHub Pages in a step-by-step guide. [Youtube link](https://www.youtube.com/watch?v=Q-YA_dA8C20)

## Prerequisites
Python<br>
VSCode<br>
Github<br>

## Procedure(default)

### Configuration validation and auto-complete(Recommended)
Add the text to vscode ==settings.json==
```yaml
{
  "yaml.schemas": {
      "https://squidfunk.github.io/mkdocs-material/schema.json": "mkdocs.yml"
  },
  "yaml.customTags": [ 
      "!ENV scalar",
      "!ENV sequence",
      "!relative scalar",
      "tag:yaml.org,2002:python/name:material.extensions.emoji.to_svg",
      "tag:yaml.org,2002:python/name:material.extensions.emoji.twemoji",
      "tag:yaml.org,2002:python/name:pymdownx.superfences.fence_code_format"
  ]
}
```

### Make github repository
Create a repository to manage your documents.

### Clone repository
Clone your repository in the location you want to work in.

### Create a virtual environment
Create a virtual environment for your mkdocs project.

### MKDocs install
```python title="Install material for mkdocs"
pip install mkdocs-material
```

### Make MKDocs project(mkdocs new .)
To create a project, at the command line, type `mkdocs new .` (where you want to create the project).
```bash title="Make MKDocs project"
mkdocs new .
```

### Set mkdocs.yml
Modify the mkdocs.yml inside your project if you need to change settings or add functionality.

### Make docs
If you create an MD file inside the docs folder of your project, the service will automatically reflect it when it runs.

### Run MKDocs 
Run the service by typing mkdocs serve at the command line (default port is 8000).
```bash
mkdocs serve
```

### Deploy
1. Make directory `.github/workflows`
2. Make file `ci.yml`
3. Input code ci.yml(use github action)
   ```yaml
    name: ci 
    on:
      push:
        branches:
          - master 
          - main
    permissions:
      contents: write
    jobs:
      deploy:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v4
          - name: Configure Git Credentials
            run: |
              git config user.name github-actions[bot]
              git config user.email 41898282+github-actions[bot]@users.noreply.github.com
          - uses: actions/setup-python@v4
            with:
              python-version: 3.x
          - run: echo "cache_id=$(date --utc '+%V')" >> $GITHUB_ENV 
          - uses: actions/cache@v3
            with:
              key: mkdocs-material-${{ env.cache_id }}
              path: .cache
              restore-keys: |
                mkdocs-material-
          - run: pip install mkdocs-material 
          - run: mkdocs gh-deploy --force
   ```

## QnA

### What if I want to adjust the order of the MD files after creating them? 
Add the nav attribute to the top-level depth in Medics.yml.
```yaml title="nav attribute in mkdocs.yml"
nav:
  - index.md 
  - getting_started.md
  - example.md
```
You can name the MD files in any order you want, as shown above, and they will be reflected in the webpage in that order. In addition, the MD files are titled in the webpage based on the titles in the markdown.


