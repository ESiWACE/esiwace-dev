SRC_DIR := dot
PDF_DIR := pdf

SRC_FILES := $(wildcard $(SRC_DIR)/*.dot)
PDF_FILES := $(patsubst $(SRC_DIR)/%.dot,$(PDF_DIR)/%.pdf,$(SRC_FILES))

$(PDF_DIR)/%.pdf: $(SRC_DIR)/%.dot
	dot -Tpdf $< -o $@
	pdfcrop $@
	mv $(PDF_DIR)/$*-crop.pdf $@
	
figs: $(PDF_FILES)
