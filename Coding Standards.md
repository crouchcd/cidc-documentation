When committing files;

* use black with default settings
* use pylint with .pylintrc files which should be in most repos already

Black doesn't have an opinion on docstring formatting, we use this

def some_method(items: List[dict]) -> List[str]:
```python
    """
    Description of method
    Arguments:
        items {[dict]} -- Argument description.
    Returns:
        [str] -- Return description.
    """
```
