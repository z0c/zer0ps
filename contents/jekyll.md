# Jakyll

Jakyll is a simple tool to make static sites out of markdown documents

## Installation

```
$ gem install bundler jekyll
$ jekyll new site-name
$ cd site-name
$ jekyll serve
```

You can browse to `http://localhost:4000` to view the site

## Building

This will regenerate the site files
```
jekyll build --source {source_path} --destination {destination_path}
```

`source` defaults to current path, `destination` defaults to `_site`. This can also been overriden in `_config.yaml`

## File and folder structure

| Item              | Description                                           |
-----------------------------------------------------------------------------
| `_config.yaml`    | Configuration data for the site                       |
| `_drafts`         | Unpublished posts, these dont need the date           |
| `_posts`          | Actual dynamic content, `YEAR-MONTH-DAY-title.MARKUP` |

## Reference

 * https://jekyllrb.com/
