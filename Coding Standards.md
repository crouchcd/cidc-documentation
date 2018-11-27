
## Formatting

When committing files;

* use black with default settings

```bash
black .
```
* use pylint with .pylintrc files which should be in most repos already

```bash
pylint .
```

Black doesn't have an opinion on docstring formatting, we use this

```python
def some_method(items: List[dict]) -> List[str]:
    """
    Description of method
    
    Annotation:
        Annotation -- Annotation description.

    Arguments:
        items {List[dict]} -- Argument description.
    
    Raises:
        SomeError -- Error description.
        
    Returns:
        List[str] -- Return description.
    """
```

## Version Control

The best format to use for GitHub issues in commit messages or branch names is

```bash
organization/repo#ticket_number
```

As an example, issue 91 in the cidc-portal repo of the DFCI organization

```bash
dfci/cidc-portal#91
```

Where possible, create branches with a name to reflect the fully qualified ticket they are addressing.

Whenever writing a commit, start with the fully qualified issue name and a dash.

```bash
git commit -m "dfci/cidc-portal#91 - Commit message here."
```
