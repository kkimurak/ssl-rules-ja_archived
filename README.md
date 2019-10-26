# RoboCup Small Size League rules

English | [Japanese](README_jp.md)

This is the AsciiDoc source for the unofficial Japanese translation of RoboCup Small Size League rules.  
The official rules can be found at [Official GitHub Repository](https://github.com/RoboCup-SSL/ssl-rules)
The legacy version of the rules can be found at [here](https://github.com/RoboCup-SSL/ssl-rules-legacy)

## Build

The rules are automatically built on updates to the master-jp branch and published to [Github Pages](https://kkimurak.github.io/ssl-rules-jp/sslrules.html). There is also a [PDF-version](https://kkimurak.github.io/ssl-rules-jp/sslrules.pdf).

### Using AsciiDoctor natively

Install [AsciiDoctor](https://asciidoctor.org/) on your system . Afterwards, build HTML5 version with

```sh
# Build the HTML5 version
asciidoctor sslrules.adoc
```

To build PDF version with Japanese characters, you can use asciidoctor-pdf-cjk-kai_gen_gothic.

```sh
# Build the PDF version
asciidoctor-pdf -r asciidoctor-pdf-cjk-kai_gen_gothic -a pdf-style=KaiGenGothicJP sslrules.adoc
```

### Using docker image

If you have Docker installed, you can use the AsciiDoctor image that optimized for Japanese:

```sh
# Pull image once
docker pull htakeuchi/docker-asciidoctor-jp
# Build the HTML5 version
docker run -v $PWD:/documents/ asciidoctor/docker-asciidoctor asciidoctor sslrules.adoc
# Build the PDF version
docker run -v $PWD:/documents/ asciidoctor/docker-asciidoctor asciidoctor-pdf -r asciidoctor-pdf-cjk-kai_gen_gothic -a pdf-style=KaiGenGothicJP sslrules.adoc
```
