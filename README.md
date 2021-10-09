# pip-conflicts
Test repository to illustrate bad conflict resolution

## How to reproduce
1. Install good
```
pip install -e . -c req_good.txt
```
Optionally, verify that all required packages have their exact version specified:
```
pip freeze > req_current.txt
diff req_good.txt req_current.txt
```
2. Try to update with different
```
pip install -e . -c req_bad.txt
```
This takes way too much time on my machine (it hasn't finished after 3 minutes).
Check that only one requirement has different version in new file:
```
diff req_good.txt req_bad.txt
```
This should not take that much time to figure out.
