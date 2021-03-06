---
layout: docs
title: Configuration
permalink: /docs/configuration/
redirect_from: /docs/editor/configuration/
---

# Configuration

Quill allows several ways to customize it to suit your needs. This section is dedicated to tweaking existing functionality. See the [Modules](/docs/modules/) section for adding new functionality and the [Themes](/docs/themes/) section for styling.


### Container

Quill requires an container where the editor will be appended. You can either pass in a CSS selector or a DOM object.

{% highlight javascript %}
var editor = new Quill('.editor');  // The first result of the selector will be used
{% endhighlight %}

{% highlight javascript %}
var container = document.getElementById('editor');
var editor = new Quill(container);
{% endhighlight %}

{% highlight javascript %}
var container = $('.editor').get(0);
var editor = new Quill(container);
{% endhighlight %}

### Options

To configure Quill, pass in an options object:

{% highlight javascript %}
var configs = {
  readOnly: true,
  theme: 'snow'
};
var editor = new Quill('#editor', configs);
{% endhighlight %}

The following keys are recognized:

#### formats

- Formats recognized by the editor. See [Formats](/docs/formats/) for more information.

#### modules

- Collection of modules to include. See [Modules](/docs/modules/) for more information.

#### pollInterval

- Default: `100`

- Number of milliseconds between checking for local changes in the editor. Note that certain actions or API calls may prompt immediate checking.

#### readOnly

- Default: `false`

- Whether to instantiate the editor to read-only mode.

#### styles

- Default: `{}`

- Object containing CSS rules to add to the Quill editor. Passing in `false` (not merely a falsy value) will prevent Quill from inserting any default styles. In this latter case it is assumed either the base stylesheet (`quill.base.css`) or a theme stylesheet is included manually.

- **Example**

{% highlight javascript %}
var editor = new Quill('#editor', {
  styles: {
    '.ql-editor': {
      'font-family': "'Arial', san-serif"
    },
    '.ql-editor a': {
      'text-decoration': 'none'
    }
  }
});
{% endhighlight %}

#### theme

- Name of theme to use. Note the theme's specific stylesheet still needs to be included manually. See [Themes](/docs/themes/) for more information.
