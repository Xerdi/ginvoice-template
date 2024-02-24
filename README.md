# GinVoice Template

An invoice template for the [GinVoice](https://gitlab.gnome.org/MacLotsen/ginvoice) application.

If you read about it in an article of MAPS or TUGboat, see the branches `maps` and `tugboat` instead.

## Usage

This branch contains two examples described in the article.

### All-in-one
The first and simplest is `all-in-one`.
You can compile PDFs using the Makefile:
```shell
make -C all-in-one template
make -C all-in-one invoice1
make -C all-in-one invoice2
```
Or you could do it manually with:
```shell
cd all-in-one
lualatex --shell-escape --jobname=invoice-001 --output-directory=../../out invoice
```

### Using TEXMF
For the second example `using-texmf` you can either use the strategy with the `-cnf-line` option which is used in the Makefile, like:
```shell
make -C using-texmf template
make -C using-texmf invoice-001
make -C using-texmf invoice-002
```
Or, if you'd like, you can place the contents of `using-texmf/texmf` directly in your own TEXMFHOME.
If you don't know the location, you can consult `kpsewhich --var-value TEXMFHOME` to get the actual path.
When having placed the contents in your own TEXMFHOME, the command is identical to the previous demo, since the `-cnf-line` option can then be omitted.

## License
This project is licensed under the GPLv3 License - see the LICENSE file for details.
