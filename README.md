![Version](https://img.shields.io/badge/version-0.1.0-orange.svg)

# Sassy Playground

Little playground to play with SASS + HTML and LiveReload.

## Install

You need **Ruby** to run this. Install required gems:

```bash
bundle install --path=vendor/bundle --binstubs
```

[guard-livereload][1] listens:

1. `*.html`
1. `public/css/*.css`
1. `public/images/*.jpg`
1. `public/images/*.png`

```ruby
guard :livereload do
  watch(%r{.+\.html})
  watch(%r{public/css/.+\.(css)})
  watch(%r{public/js/.+\.(js)})
  watch(%r{public/images/.+\.(jpg|png)})
end
```


---

## Run

```bash
rake             # runs dev server on port 5555
rake run[9191]   # runs dev server on port 9191
```

---

## Contributer(s)

* [Uğur "vigo" Özyılmazel](https://github.com/vigo) - Creator, maintainer

---

## Contribute

All PR’s are welcome!

1. `fork` (https://github.com/vigo/sassy-playground/fork)
1. Create your `branch` (`git checkout -b my-features`)
1. `commit` yours (`git commit -am 'added killer options'`)
1. `push` your `branch` (`git push origin my-features`)
1. Than create a new **Pull Request**!

---

## License

This project is licensed under MIT

[1]: https://github.com/guard/guard-livereload