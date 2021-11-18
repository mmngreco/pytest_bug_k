# pytest_bug_k


```bash
git clone --recurse-submodules https://github.com/mmngreco/pytest_bug_k
pip install -e ./pytest_bug_k
```

## Example

```python

================================================= 2 passed, 2 deselected in 0.01s =================================================
(python37) pytest_bug_k (master) (10:43|0s) $ pytest tests -v -k "not foo"
======================================================= test session starts =======================================================
platform linux -- Python 3.7.11, pytest-6.2.5, py-1.11.0, pluggy-1.0.0
rootdir: /home/mgreco/etsgit/COM/libraries/pytest_bug_k, configfile: pytest.ini
collected 5 items / 2 deselected / 3 selected

tests/test_simple.py .                                                                                                      [ 33%]
tests/module/test_module_simple.py .                                                                                        [ 66%]
tests/submodule/test_parent.py .                                                                                            [100%]

================================================= 3 passed, 2 deselected in 0.01s =================================================
(python37) pytest_bug_k (master) X (10:45|0s) $ pytest tests -v -k "not submodule"
======================================================= test session starts =======================================================
platform linux -- Python 3.7.11, pytest-6.2.5, py-1.11.0, pluggy-1.0.0
rootdir: /home/mgreco/etsgit/COM/libraries/pytest_bug_k, configfile: pytest.ini
collected 5 items / 2 deselected / 3 selected

tests/test_simple.py .                                                                                                      [ 33%]
tests/module/test_module_simple.py .                                                                                        [ 66%]
tests/submodule/foo/test_sub_simple.py .                                                                                    [100%]


================================================= 4 passed, 1 deselected in 0.01s =================================================
(python37) pytest_bug_k (master) X (10:46|1s) $ pytest tests -v -k "not (submodule or foo)"
======================================================= test session starts =======================================================
platform linux -- Python 3.7.11, pytest-6.2.5, py-1.11.0, pluggy-1.0.0
rootdir: /home/mgreco/etsgit/COM/libraries/pytest_bug_k, configfile: pytest.ini
collected 5 items / 3 deselected / 2 selected

tests/test_simple.py .                                                                                                      [ 50%]
tests/module/test_module_simple.py .                                                                                        [100%]


(python37) pytest_bug_k (master) X (10:47|0s) $ pytest tests -v -k "not submodule"
======================================================= test session starts =======================================================
platform linux -- Python 3.7.11, pytest-6.2.5, py-1.11.0, pluggy-1.0.0
rootdir: /home/mgreco/etsgit/COM/libraries/pytest_bug_k, configfile: pytest.ini
collected 5 items / 2 deselected / 3 selected

tests/test_simple.py .                                                                                                      [ 33%]
tests/module/test_module_simple.py .                                                                                        [ 66%]
tests/submodule/foo/test_sub_simple.py .                                                                                    [100%]

================================================= 3 passed, 2 deselected in 0.01s =================================================
```
