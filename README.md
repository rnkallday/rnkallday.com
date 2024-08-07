
This is a configured Hugo static website with the [arts-link.com](https://www.arts-link.com/) [Ryder theme](https://github.com/arts-link/ryder) installed. Just click the `Use this Template` button above and clone this into your own repository and start creating content. To publish your website freely on github pages, you simple need to have your forked repo be public, enable pages and set it to run with a custom github action. The action which is included here is in `.github/workflows` and only currently has a `workflow_action` meaning you need to trigger the build and deployment from the github actions dashboard. If you uncomment the lines for push to branches main under the `on:` section it will automatically deploy when you commit code to the `main` branch.

# QUICK START

- Update submodules with `git submodule update --init`
- Install javascript dependencies with `npm i`

# More details

## Git Submodules

This project uses [the Ryder Theme for Hugo websites](https://www.github.com/arts-link/ryder/) as a submodule.

If you are running locally you will need to run `git submodule update --init` to make sure your theme is up to date. If using this in a CI/CD build flow just make sure your checkout step includes submodules. For instance on github pages your workflow needs this step.

```
- name: Checkout
        uses: actions/checkout@v4
        with:
          submodules: recursive
```

# Javascript

The ryder theme uses [`fontawesome`](https://www.fontawesome.com) for icons, [`alpine.js`](https://www.alpinejs.com) for a lightweight javascript utility library, [`leaflet`](https://www.leafletjs.com) the awesome library for including and customizing all sorts of maps and [`tailwindcss`](https://www.tailwindcss.com) (which isn't javascript, but does requrie some npm packages for installation and css building).

Here is the full list of packages installed.

```
  "devDependencies": {
    "@tailwindcss/typography": "^0.5.10",
    "autoprefixer": "^10.4.16",
    "postcss": "^8.4.33",
    "postcss-cli": "^11.0.0",
    "postcss-import": "^16.0.0",
    "tailwindcss": "^3.4.1"
  },
  "dependencies": {
    "@alpinejs/focus": "^3.13.7",
    "@fortawesome/fontawesome-svg-core": "^6.5.2",
    "@fortawesome/free-brands-svg-icons": "^6.5.2",
    "@fortawesome/free-regular-svg-icons": "^6.5.2",
    "@fortawesome/free-solid-svg-icons": "^6.5.2",
    "alpinejs": "^3.13.7",
    "leaflet": "^1.9.4"
  }
```