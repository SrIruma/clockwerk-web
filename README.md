# clockwerk-web

The documentation site for [Clockwerk](https://github.com/SrIruma/clockwerk-web).

It's a static site — plain HTML, CSS and JavaScript, no build step. Open
`index.html` and it works.

Published at <https://sriruma.github.io/clockwerk-web/>.

## Pages

One view with two sections, switched with the sidebar and searchable with the
box in the top bar (press `/` to jump to it):

- **Documentation** — overview, installation, commands, permissions,
  schedules, cron, task types, missed-run policies, configuration, languages
  and placeholders.
- **API** — how to use the API, the reference, the events and the downloads.

## API jars

`api/` holds the compiled integration API the docs link to
(`clockwerk-api.jar`, `clockwerk-api-sources.jar` and
`clockwerk-api-javadoc.jar`). Rebuild them from the plugin repo with
`mvn clean package` and copy the three jars from `api/target/` back here.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

Serving it over HTTP (rather than opening the file directly) mirrors how it
behaves on Pages.

## Buy link

The "Buy on BuiltByBit" buttons in `index.html` link to
<https://builtbybit.com/resources/clockwerk.133354>. Update both occurrences if
the listing URL ever changes.

## BuiltByBit bio

`Bio.txt` holds the BBCode description for the marketplace listing. Keep the
tags as they are and edit only the text between them.

## Editing the docs

Each page is a `<section class="page">` in `index.html`. The sidebar, search
index and page title are all built from the section's `data-group`,
`data-title` and `data-keywords` attributes, so a new section shows up on its
own. Link between pages with a pager anchor carrying `data-goto="<page-id>"`.

## License

MIT for the site content. The Clockwerk plugin itself is proprietary and is
sold on BuiltByBit; the API is free to use.
