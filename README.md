# Jekyll Resize
> Image resizing tag for Jekyll 4


Forked from [CloudCannon/jekyll-resize](https://github.com/CloudCannon/jekyll-resize) to add Jekyll 4 support. In particular, by updating `.gemspec` to use Jekyll 4 and adding `require "mini_magick"` to the `.rb` file to avoid a runtime error not present on Jekyll 3.


## Requirements

- Ruby
- Jekyll 4
- GraphicsMagick

### Internal dependencies

- [minimagick/minimagick](https://github.com/minimagick/minimagick)
    - > A ruby wrapper for ImageMagick or GraphicsMagick command line.
    - Sample use is covered in the readme - e.g. `image.resize "100x100"`.


## Installation

### Install system dependencies

- Install GraphicsMagick.
    - [gist instructions](https://gist.github.com/MichaelCurrin/32b88b2c70c59832c922bcf03bdc08c3).
- Install Ruby and Bundler.
    - [gist instructions](https://gist.github.com/MichaelCurrin/3af38fca4e2903cdedfb8402c18b2936).

### Install project dependencies

1. Recommended - add Jekyll as a project gem:
  ```ruby
  source 'https://rubygems.org'

  gem 'jekyll', '~> 4.0.1'
  ```
1. Add the gem to your project's `Gemfile`:
    ```ruby
    group :jekyll_plugins do
    gem 'jekyll-resize', git: 'https://github.com/MichaelCurrin/jekyll-resize'
    end
    ```
1. Install your project's gems - using Bundler is recommended.
    ```sh
    $ bundle install
    ```

## Usage

This plugin makes the `resize` tag available.

```
resize: OPTIONS
```

### Examples

```liquid
{{ image_path | resize: "800x800>" }}
```

```liquid
[My image]({{ image_path | resize: "800x800>" }})
```

Sample Logged output on building a Jekyll site:

```
Thumbnailing .../my-project/uploads/1.jpg to .../my-project/cache/resize/c673c80c6..._800x800.jpg (800x800>)
```

## Development

Commit and push changes. You do not need to tag.

Run this in another project to get the latest version of the gem.

```sh
$ bundle update
```


## License

Released under [MIT](/LICENSE).

Original license - [MIT](/LICENSE-source).
