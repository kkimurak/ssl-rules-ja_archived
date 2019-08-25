# ロボカップ小型機リーグルール

ロボカップ小型機リーグ(SSL)公式ルールの、AsciiDoc形式のソースコードです。  
旧バージョンのルール(英語)は https://github.com/RoboCup-SSL/ssl-rules-legacy よりご覧いただけます。

## ビルド

ルールはmaster-jpブランチの更新に応じて、自動的に[Github Page](https://kkimurak.github.io/ssl-rules-jp/sslrules.html)に公開されます。[PDF版](https://kkimurak.github.io/ssl-rules-jp/sslrules.pdf)もご利用いただけます。

### ネイティブ版AsciDoctorの使用

AsciiDoctorをインストールしてください(https://asciidoctor.org/)。その後、以下のコマンドでHTML5版をビルドできます :
```
# HTML5版のビルド
asciidoctor sslrules.adoc
```

日本語を含むPDFを生成する場合、asciidoctor-pdf-cjk-kai_gen_gothicを使うと良いでしょう :
```
# Build the PDF version
asciidoctor-pdf -r asciidoctor-pdf-cjk-kai_gen_gothic -a pdf-style=KaiGenGothicJP sslrules.adoc
```

### dockerイメージの使用

Dockerをインストールしているのであれば、日本語環境向けに最適化されたAsciiDoctorイメージを使うことができます :
```
# dockerイメージをpullする
docker pull htakeuchi/docker-asciidoctor-jp
# HTML5版のビルド
docker run -v $PWD:/documents/ asciidoctor/docker-asciidoctor asciidoctor sslrules.adoc
# Build the PDF version
docker run -v $PWD:/documents/ asciidoctor/docker-asciidoctor asciidoctor-pdfasciidoctor-pdf -r asciidoctor-pdf-cjk-kai_gen_gothic -a pdf-style=KaiGenGothicJP sslrules.adoc
```
