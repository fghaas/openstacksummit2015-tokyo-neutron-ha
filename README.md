# Clusters, Routers, Agents and Networks
High Availability in Neutron

OpenStack Summit Tokyo 2015

Presenters:
- Florian Haas, hastexo
- Assaf Muller, Red Hat
- Adam Spiers, SUSE

## Contributing

- Fork this repository.
- Create a local checkout of your fork, tracking the `master` and
  `gh-pages` branches.
- Make changes in your `master` branch. Presentation text is in
  Markdown and goes into the `markdown` directory; any images should
  be PNG or JPEG (for photos) or SVG (for graphics) and go into
  `images`.
- Commit in your master branch and send a pull request.

### Demos

We'll be using Asciinema for demos. In order to do so, run your demo
in `script`, like so:

```bash
$ script --timing=demo.timing demo.script
```

This opens up a new shell that has all its terminal output
recorded. When your demo is complete, type `exit` or hit `Ctrl-D` to
close the shell. Then send Florian both generated files and he takes
care of turning them into an asciicast.

## Checking your work

- Merge `master` into `gh-pages`.
- Push `gh-pages` to your fork. The presentation then auto-renders
  using GitHub Pages.
- Open http://username.github.io/openstacksummit2015-tokyo-neutron-ha,
  replacing `username` with your GitHub user name.

### Running things locally

If you want to run your slides locally, rather than on GitHub Pages,
just drop them into the DocumentRoot of a web server, like Apache or
lighttpd (lighty).

For lighttpd, you may also want to set the following options:

```
dir-listing.encoding = "utf-8"
server.dir-listing   = "enable"
server.modules      += ( "mod_userdir" )
userdir.path         = "public_html"
```

Then, create a symlink to your Git checkout in `~/public_html`, such as:

```bash
ln -s ~/git/openstacksummit2015-tokyo-neutron-ha ~/public_html/
```

... and access your presentation from
http://localhost/~yourusername/openstacksummit2015-tokyo-neutron-ha/.