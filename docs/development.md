# Development

Yu could say there  are two different stages to devloping Kanmail:

1. "Proper" dev - flask dev server w/reload + webpack(-dev-server)
2. "Testing" dev - run as an app, using pywebview, flask w/o reload + webpack

The first is much better for normal dev because you get the full suite of devtools from Firefox (or Chrome, if you must). The testing stage is a proper end-to-end experience with the whole app being tested/rendered, but the webkit devtools are awful, and no flask reloading is a deal-breaker for any backend work.

Version numbers are generated at build in the date-based format: `MAJOR.YYMMDDhhmm`.

### MacOS

Whatever Python version/virtualenv/pyenv combo you choose to use - most importantly note that to run the app itself (rather than via a browser), Python _must_ be configured `--with-framework`. See [this StackOverflow answer](https://stackoverflow.com/a/15752676/352488) to to check whether this is enabled.

```
# Install the MacOS requirements
pip install -r requirements/macos.pip`

# Start the server+webpack-server
honcho start

# OR - start the app itself (full pywebview window with debug - right click)
honcho start -f Procfile-app
```