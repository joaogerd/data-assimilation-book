#======================================================================
# Makefile — Compilação do livro "Introdução à Assimilação de Dados"
# Autor: João Gerd Zell de Mattos
# Local: src/
# Uso:
#   make            → compila o PDF final (latexmk + biber)
#   make clean      → remove arquivos temporários
#   make view       → abre o PDF
#   make draft      → compila versão de rascunho (sem limpeza)
#======================================================================

# Nome-base do arquivo principal (sem extensão)
MAIN = main

# Compilador LaTeX
LATEXMK = latexmk
LATEXMK_OPTS = -pdf -interaction=nonstopmode -halt-on-error

#======================================================================
# Regras principais
#======================================================================

# Compilação padrão (usa latexmk com biber)
all: $(MAIN).pdf

$(MAIN).pdf: $(MAIN).tex
	@echo "[INFO] Compilando o livro..."
	$(LATEXMK) $(LATEXMK_OPTS) $(MAIN).tex
	@echo "[OK] PDF gerado: $(MAIN).pdf"

# Visualizar PDF (Linux)
view: $(MAIN).pdf
	@echo "[INFO] Abrindo PDF..."
	xdg-open $(MAIN).pdf >/dev/null 2>&1 &

# Compilação de rascunho (sem limpeza, útil para escrever)
draft:
	@echo "[INFO] Compilando versão de rascunho..."
	$(LATEXMK) -pdf -pvc $(MAIN).tex

force:
	@echo "[INFO] Compilando o livro..."
	$(LATEXMK) $(LATEXMK_OPTS) -f $(MAIN).tex
	@echo "[OK] PDF gerado: $(MAIN).pdf"

#======================================================================
# Limpeza de artefatos temporários
#======================================================================
clean:
	@echo "[INFO] Removendo arquivos temporários..."
	$(LATEXMK) -C
	rm -f *.glg *.glo *.gls *.ist *.acn *.acr *.alg *.bbl *.bcf *.blg *.run.xml
	@echo "[OK] Limpeza concluída."

#======================================================================
# Limpeza completa (inclui PDF)
#======================================================================
cleanall: clean
	rm -f $(MAIN).pdf
	@echo "[OK] Todos os arquivos removidos."

#======================================================================
# Dependências auxiliares
#======================================================================
.PHONY: all clean cleanall view draft

