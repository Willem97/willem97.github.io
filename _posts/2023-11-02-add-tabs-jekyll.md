---
layout: post
title: Add tabs for jekyll
date: 2023-09-11 15:09:00
description: Add code tabs for jekyll themem.
tags: tutorial
categories: tutorial
featured: false
toc:
    sidebar: left
---

## Install the plugin

Add `jekyll-tabs` in `Gemfile`

```gemfile
group :jekyll_plugins do
  # ... other gems
  gem "jekyll-tabs"
end
```

Add `jekyll-tabs` in `_config.yaml`

```yaml
# Plug-ins
plugins:
    # ... other plugins
    - jekyll-tabs
```

Modify `docker-compose.yaml` to build your own version. For example, your name as `foo`, and al-folio version is `v0.10.1`.

```yaml
version: "3"
# this file uses prebuilt image in dockerhub
services:
    jekyll:
        image: foo/al-folio:v0.10.1
        # ...
```

After that, build your own docker image and push to docker hub.

## Include the javascript

Copy the content of [this file](https://raw.githubusercontent.com/awslabs/aws-ddk/main/docs/assets/js/tabs.js) in your public folder (for example `assets/js/tabs.js`)

```html
<!DOCTYPE html>
<html lang="en-us">
    <head>
        ...
    </head>
    <body>
        <script src="/assets/js/tabs.js"></script>
    </body>
</html>
```

## Add tabs style

Copy the content of [this file](https://raw.githubusercontent.com/Ovski4/jekyll-tabs/master/docs/tabs.css) in your public folder (for example `assets/css/tabs.css`)

```html
<!DOCTYPE html>
<html lang="en-us">
    <head>
        ...
        <link rel="stylesheet" href="/assets/css/custom.css" />
    </head>
    <body>
        ....
    </body>
</html>
```

## Demo

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/blog/tabs.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

{% tabs log %}

{% tab log Table1 %}

table 1

{% endtab %}

{% tab log Table3 %}

table 2

{% endtab %}

{% tab log Table3 %}

table 3

{% endtab %}

{% endtabs %}

## Reference

-   https://github.com/Ovski4/jekyll-tabs
-   https://github.com/awslabs/aws-ddk
