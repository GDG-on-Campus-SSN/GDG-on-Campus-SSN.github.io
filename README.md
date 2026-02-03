# GDG on Campus SSN Website

This is the source for the GDG SSN Website. It is a zola SSG (static site generator) project.
Modify the files in `content/blog/` for new blog posts. You can find the actual html code in `templates/`.
CSS styles are in `static/styles/`.

## Developing

You can see the site by running
```bash
zola serve
```
You can build to site to `public/` by running
```bash
zola build
```
Checkout the zola docs for more info.

For publishing, use the Zola [github action](https://www.getzola.org/documentation/deployment/github-pages/), to put it on github pages.

I'm tyring to get github action to run
