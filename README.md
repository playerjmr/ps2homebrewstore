## Contributing

Made with [Material for MKDocs](https://squidfunk.github.io/mkdocs-material/)

Downloads hosted at https://downloads.ps2homebrewstore.com which is Cloudflare R2. Right now only main web-dev has access to upload and maintain. 

To help with the project, you may reach R3Z3N the webdev on [Discord](https://discord.com/users/693253444059791440)

Uploads need to be verified so SAS/UMCS team can approve, hence why Cloudflare R2 does not yet have a pulbic bucket.

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