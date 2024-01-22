# Markdown example

## Code Annotation Example 

### Codeblocks

This is `code` Block

### Plain codeblocks
```
This is plane codeblock
```

### Python codeblocks
``` py
def sum(a, b):
    answer = a + b
    return answer
```

### Yaml codeblocks
```yaml
palette:  
    - media: "(prefers-color-scheme: light)" 
      scheme: default 
      primary: blue grey 
      accent: indigo 
      toggle: 
        icon: material/brightness-7 
        name: Switch to dark mode
```

### with a title
``` py title="Title codeblock"
def multiply(a, b)
    answer = a * b
    return answer
```

### with line numbers
```py title="Linenums" linenums="1"
def multiply(a, b)
    answer = a * b
    return answer
```

### Highlighting lines
```py title="Line highlight" hl_lines="2 3"
def multiply(a, b)
    answer = a * b
    return answer
```

## Icons and Emojs
[Emojs reperence](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md)

:smile:

:slightly_smiling_face:

:fontawesome-regular-face-laugh-wink:

## Admonitions
[Admonitions reperences](https://squidfunk.github.io/mkdocs-material/reference/admonitions/#inline-blocks-inline-end)

### default
!!! note
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.


### collapsible and initially expanded
??? note
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.

### Warning
!!! warning
    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla et euismod
    nulla. Curabitur feugiat, tortor non consequat finibus, justo purus auctor
    massa, nec semper lorem quam in massa.