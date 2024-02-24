
OUTPUT_DIR ?= ../../out
CNF_LINE = -cnf-line TEXMFHOME={../texmf,$(shell kpsewhich --var-value TEXMFHOME)}

%.pdf:
	lualatex --interaction=nonstopmode --shell-escape $(CNF_LINE) \
			 --output-directory=$(OUTPUT_DIR) \
			 --jobname=$* \
			   invoice
	cd $(OUTPUT_DIR) && latexmk -c $*.aux

template: invoice2-template.pdf

invoice1: invoice2-001.pdf

invoice2: invoice2-002.pdf

all: template invoice1 invoice2
