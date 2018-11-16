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
