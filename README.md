RAML Mock-ups!
==============

Fork of the [https://github.com/gextech/raml-mockup](gextech/raml-mockup) repo.

Original repo mostly relies on RAML 0.8 schema definitions, not on 1.0 types. The goal if this project is to implement
better support for 1.0 features, types in particular. 

Features
--------

- Uses `json-schema-faker` for accurate mocked responses (for 0.8 schemas).
- Uses `refaker` for resolving remote/local $refs (for 0.8 schemas).
- It's fully tested and coveraged.
- Has watch mode built-in.

Improvements in comparison to the original fork
--------

- Supports all content types, not only `application/json`
- Readme tweaks

How to setup & use
--------

Install `raml-1-mockup` globally:

```bash
$ npm install -g raml-1-mockup
```

Then starts a mock-server from your RAML:

```bash
$ raml-1-mockup src/api.raml -p 5000 -w
```

Now you can make requests through the mocked-API:

```bash
$ http http://localhost:5000/path/to/resource
```

The better if you're using [httpie](https://github.com/jakubroztocil/httpie).

Options
-------

General
-----------

- `--timeout` &rarr; Timeout requests from remote dereferencing.
- `--silent` &rarr; Turns off the reporting through the STDOUT.
- `--watch` &rarr; Enables the watch mode for mock-server.
- `--port` &rarr; Custom port for mock-server.
- `--statuses` &rarr; Use custom statusCode(s) for all matched resources.

Mocking for 0.8 schema definitions
-----------

- `--directory` &rarr; Used with `--fakeroot` to resolve _faked_ references through this directory.
- `--fakeroot` &rarr; BaseURI for references that will fake (i.e. `http://json-schema.org`).
- `--formats` &rarr; CommonJS module-id or path for custom formats.

Run `raml-1-mockup -h` to display all usage info.

queryParams
-----------

Use the following options for custom responses:

- `_statusCode=200` &rarr; Force a specific statusCode if its available.
- `_forceExample=true` &rarr; Force defined resource-example if its available.

Issues?
-------

Please open a ticket or feel free for contributing.

Development
-------

Install `jasmine-node`:

```bash
$ npm install -g jasmine-node
```
