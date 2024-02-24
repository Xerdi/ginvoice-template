WATCH_TARGET ?= invoice-template
OUTPUT_DIR ?= ../out

%.pdf:
	lualatex --shell-escape \
  			 --jobname=$* \
  			 --output-directory=$(OUTPUT_DIR) \
  			   invoice
	cd $(OUTPUT_DIR) && latexmk -c $*.aux

template: invoice-template.pdf

invoice1: invoice-001.pdf

invoice2: invoice-002.pdf

all: template invoice1 invoice2

watch:
	latexmk -pvc -lualatex --shell-escape \
			--jobname=$(WATCH_TARGET) \
			--output-directory=$(OUTPUT_DIR) \
			  invoice
