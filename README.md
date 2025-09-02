## Contributing

### Dependencies

This project requires [python and pip](https://www.python.org/).

Check pip is properly installed by running `pip --version`.

Install mkdocs and related plugins. You might need to run these as admin on windows.
```
pip install mkdocs
pip install mkdocs-material
pip install mkdocs-glightbox
```

### Working with mkdocs

You can run `mkdocs build` from the root of the project. This will build the project and output the html website in `/site`.

If you are actively working on the md files, css, or js, you can use `mkdocs serve -o`. This will open the website in your browser, and observe the project files for change. If a files is modified, `serve` will automatically rebuild and then refresh the browser.