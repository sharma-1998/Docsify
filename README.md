# Introduction :-

Docsify is a lightweight, flexible, and easy-to-use documentation generator that is primarily designed for creating documentation websites. It allows you to turn your markdown files into a documentation site that is clean, organized, and user-friendly.

## Features :-

- No statically built html files
- Simple and lightweight
- Smart full-text search plugin
- Multiple themes
- Useful plugin API
- Emoji support
- Emoji support
- Support server-side rendering

## Benefits of Docsify :-

- all-in-one email tracking
- one-minute installation
- easy-to-usee interface
- 24/7 customer support
- Free plan forever

## Setup by Docsify :-

### Requirement of Docsify

Docsify comes with lots of customization options, and you don't need any additional knowledge to configure it – it's pretty straightforward.

## Install Node.js:-

```

 sudo apt install nodejs
```

 >Output

[sudo] password for vishal
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
nodejs is already the newest version (18.19.0-1nodesource1).
0 upgraded, 0 newly installed, 0 to remove and 11 not upgraded.

```

sudo apt install npm

```

 >Output:

Reading package lists... Done  
Building dependency tree... Done  
Reading state information... Done  
Some packages could not be installed. This may mean that you have
requested an impossible situation or if you are using the unstable
distribution that some required packages have not yet been created
or been moved out of Incoming.
The following information may help to resolve the situation:

## Check Version:-

```

node -v

```

> Output:-

v18.19.0

```

 npm -v

```

> Output:-


10.2.5

## Create a New Project :-

```

mkdir my-doce

```

```

cd my-doce
```

## Initialize npm:-

```

npm init -y
```

## Install Docsify:-

```

npm install docsify-cli 
```

## Create Docsify Files:-


touch Index.html README.md

cd README.md

docsify serve

 http://localhost:3000 


 ## Configuration:-

 ou can configure Docsify by defining window.$docsify as an object:

```

<script>
  window.$docsify = {
    repo: 'docsifyjs/docsify',
    maxLevel: 3,
    coverpage: true,
  };
</script>
```

The config can also be defined as a function, in which case the first argument is the Docsify vm instance. The function should return a config object. This can be useful for referencing vm in places like the markdown configuration:

```

<script>
  window.$docsify = function (vm) {
    return {
      markdown: {
        renderer: {
          code(code, lang) {
            // ... use `vm` ...
          },
        },
      },
    };
  };
</script>

```

> alias

- Type: Object

Set the route alias. You can freely manage routing rules. Supports RegExp. Do note that order matters! If a route can be matched by multiple aliases, the one you declared first takes precedence.

```

window.$docsify = {
  alias: {
    '/foo/(.*)': '/bar/$1', // supports regexp
    '/zh-cn/changelog': '/changelog',
    '/changelog':
      'https://raw.githubusercontent.com/docsifyjs/docsify/master/CHANGELOG',
    '/.*/_sidebar.md': '/_sidebar.md', // See #301
  },
};
```

## Custom navbar

Alternatively, you can create a custom markdown-based navigation file by setting loadNavbar to true and creating _navbar.md, compare loadNavbar configuration.

```

<!-- index.html -->

<script>
  window.$docsify = {
    loadNavbar: true
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
```
<!-- _navbar.md -->

```

* [En](/)
* [chinese](/zh-cn/)
```

## Markdown

Alternatively, you can create a custom markdown-based navigation file by setting loadNavbar to true and creating _navbar.md, compare loadNavbar configuration.

```

<!-- index.html -->

<script>
  window.$docsify = {
    loadNavbar: true
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>

<!-- _navbar.md -->
```

## Navigation and Sidebar:-


### Navigation

### Sidebar:-

In order to have a sidebar, you can create your own _sidebar.md (see this documentation's sidebar for an example):

First, you need to set loadSidebar to true. Details are available in the configuration paragraph.

```

<!-- index.html -->

<script>
  window.$docsify = {
    loadSidebar: true
  }
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
```

Create the _sidebar.md:

```

<!-- docs/_sidebar.md -->

* [Home](/)
* [Guide](guide.md)
```

## Configuration

You can configure Docsify by defining window.$docsify as an object:

```

<script>
  window.$docsify = {
    repo: 'docsifyjs/docsify',
    maxLevel: 3,
    coverpage: true,
  };
</script>
```

The config can also be defined as a function, in which case the first argument is the Docsify vm instance. The function should return a config object. This can be useful for referencing vm in places like the markdown configuration:
```
<script>
  window.$docsify = function (vm) {
    return {
      markdown: {
        renderer: {
          code(code, lang) {
            // ... use `vm` ...
          },
        },
      },
    };
  };
</script>
```

> alias

- Type: Object


Set the route alias. You can freely manage routing rules. Supports RegExp. Do note that order matters! If a route can be matched by multiple aliases, the one you declared first takes precedence.

```

window.$docsify = {
  alias: {
    '/foo/(.*)': '/bar/$1', // supports regexp
    '/zh-cn/changelog': '/changelog',
    '/changelog':
      'https://raw.githubusercontent.com/docsifyjs/docsify/master/CHANGELOG',
    '/.*/_sidebar.md': '/_sidebar.md', // See #301
  },
};
```

## GitHub :-

There are three places to populate your docs for your GitHub repository:

- docs/ folder

- main branch

- gh-pages branch

It is recommended that you save your files to the ./docs subfolder of the main branch of your repository. Then select main branch /docs folder as your GitHub Pages source in your repository's settings page.

 ## GitLab Pages

 If you are deploying your master branch, create a .gitlab-ci.yml with the following script:

The .public workaround is so cp doesn't also copy public/ to itself in an infinite loop.

```

pages:
  stage: deploy
  script:
  - mkdir .public
  - cp -r * .public
  - mv .public public
  artifacts:
    paths:
    - public
  only:
  - master
  ```

 ##  Available Plugins and Extensions:

### Google Analytics

Install the plugin and configure the track id.

```

<script>
  window.$docsify = {
    ga: 'UA-XXXXX-Y',
  };
</script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js"></script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/ga.min.js"></script>

Configure by data-ga.

<script src="//cdn.jsdelivr.net/npm/docsify/lib/docsify.min.js" data-ga="UA-XXXXX-Y"></script>
<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/ga.min.js"></script>
```

 ## Emoji

Renders a larger collection of emoji shorthand codes. Without this plugin, Docsify is able to render only a limited number of emoji shorthand codes.
```

Deprecated as of v4.13. Docsify no longer requires this plugin for full emoji support.
```

```


<script src="//cdn.jsdelivr.net/npm/docsify/lib/plugins/emoji.min.js"></scrip
```

## Steps for deploying Docsify

### Initialize

```

docsify inti .

```

### output

> Initiazation succeeded ! Pleas run docsify serve .

## Advanced customization 

## Themes

There is a handful of themes available, both official and community-made. Copy Vue and buble website custom theme and @liril-net contribution to the theme of the black style.

```

<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/vue.css" />
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/buble.css" />
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/dark.css" />
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/themes/pure.css" />

```

```

<!-- compressed -->

<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/lib/themes/vue.css" />
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/lib/themes/buble.css" />
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/lib/themes/dark.css" />
<link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify/lib/themes/pure.css" />


```