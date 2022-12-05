
## Edit and Debug

Different developers have different document maintenance habits, 
it is recommended to maintain the document with a separate `docs: xxxx` branch 
instead of directly making Pull Requests to the master branch.

When debugging locally, we usually use two instructions:

```shell
.\make.bat clean              
.\make.bat html
```

Note: 

- Make sure the current path is under the `docs` folder and have installed all things in `requirements.txt`.
- `clean` operation must be performed before `build`, otherwise undetectable errors may occur.

## Push to GitHub

In order to simplify the code review process and reduce `.git` size, changes to the `_build` folder are usually not logged.
(Check the `.gitignore` file in the root path of the project and find `docs/_build/` line for Sphinx documentation)
Only the contents in the `_source` folder will be submitted to GitHub (unless `_template` or `_theme` is used).

## Build and Host on Readthedocs

Readthedocs detect changes to the source code of the document through webhooks, 
after the source code is updated, you need to check whether the document hosted in readthedocs is successfully built.