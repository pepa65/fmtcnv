# fmtcnv 2.3.13
[![version](https://img.shields.io/crates/v/fmtcnv.svg)](https://crates.io/crates/fmtcnv)
[![build](https://github.com/pepa65/fmtcnv/actions/workflows/ci.yml/badge.svg)](https://github.com/pepa65/fmtcnv/actions/workflows/ci.yml)
[![coverage](https://github.com/pepa65/fmtcnv/blob/coverage/htmlcov/badges/flat.svg)](https://github.com/pepa65/fmtcnv/blob/coverage/htmlcov/index.html)
[![dependencies](https://deps.rs/repo/github/pepa65/fmtcnv/status.svg)](https://deps.rs/repo/github/pepa65/fmtcnv)
[![docs](https://img.shields.io/badge/docs-fmtcnv-blue.svg)](https://docs.rs/crate/fmtcnv/latest)
[![license](https://img.shields.io/badge/License-Apache-blue.svg)](https://github.com/pepa65/fmtcnv/blob/main/LICENSE)
[![downloads](https://img.shields.io/crates/d/fmtcnv.svg)](https://crates.io/crates/fmtcnv)

**This crate 'fmtcnv' is the continuation of crate 'convfmt'
which uses the unmaintained and outdated crate 'hocon'
(replaced here with 'hocon_')**

The command line tool [fmtcnv](https://github.com/pepa65/fmtcnv) converts between these formats:
* [bson](https://en.wikipedia.org/wiki/BSON)
* [csv](https://en.wikipedia.org/wiki/Comma-separated_values)
* [hjson](https://hjson.github.io/)
* [hocon](https://github.com/lightbend/config/blob/main/HOCON.md)
* [json](https://en.wikipedia.org/wiki/JSON)
* [json5](https://en.wikipedia.org/wiki/JSON5)
* [jsonl](https://jsonltools.com/what-is-jsonl)
* [plist](https://en.wikipedia.org/wiki/Property_list)
* [ron](https://github.com/ron-rs/ron)
* [toml](https://en.wikipedia.org/wiki/TOML)
* [toon](https://toonformat.dev/)
* [xml](https://en.wikipedia.org/wiki/XML)
* [yaml](https://en.wikipedia.org/wiki/YAML)

## Usage
```
fmtcnv 2.3.13 - Cross-convert bson, csv, hjson, hocon, json, json5, jsonl, plist, ron, toml, toon, xml, yaml
Convert formats from stdin to stdout. Repo: github.com/pepa65/fmtcnv
Usage: fmtcnv [OPTIONS] --from <FROM> --to <TO>
Options:
  -f, --from <FROM>  [possible values: bson, csv, hjson, hocon, json, json5, jsonl, plist, ron, toml, toon, xml, yaml]
  -t, --to <TO>      [possible values: bson, csv, hjson, hocon, json, json5, jsonl, plist, ron, toml, toon, xml, yaml]
  -c, --compact      Compact output as much as possible [default: false]
  -h, --help         Print help
  -V, --version      Print version
```

## Examples
```
cat cfg.yml |fmtcnv -f yaml -t toml >cfg.toml
fmtcnv -f json -t json <compact.json >pretty.json
curl https://api.github.com/users/pepa65 |fmtcnv -f json -t json5  # Output on stdout
```

**Beware of `null` values, as some formats (toml!) don't support them.**

## Installation
* Download latest [binary](https://github.com/pepa65/fmtcnv/releases)
* Install binary using [cargo-binstall](https://github.com/cargo-bins/cargo-binstall):
  `cargo install cargo-binstall && cargo binstall fmtcnv`
* Build [crate](https://crates.io/crates/fmtcnv) from crates.io with [rust](https://www.rust-lang.org/tools/install):
  `cargo install fmtcnv`
* Build [repo](https://github.com/pepa65/fmtcnv) locally with [rust](https://www.rust-lang.org/tools/install):
```
git clone https://github.com/pepa65/fmtcnv
cd fmtcnv
cargo rel
```
