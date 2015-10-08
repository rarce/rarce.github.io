rarce.github.io
===============
Blog personal en jekyll

Commands
--------

Jekyll
```
# The current folder will be generated into ./_site
jekyll build

# The current folder will be generated into ./_site,
# watched for changes, and regenerated automatically.
jekyll build --watch

# A development server will run at http://localhost:4000/
jekyll serve

```

Update

```
gem update github-pages
```

Redirect From Plugin
____________________

To redirect a page from /foo, add the following to the top of the page:

---
redirect_from: "/foo"
---
