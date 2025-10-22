# Introdução à Assimilação de Dados

Livro em desenvolvimento por **João Gerd Zell de Mattos**.  
Foco: fundamentos, prática e perspectivas da assimilação de dados aplicada à previsão numérica.

## Estrutura
```

data-assimilation-book/
│
├── src/
│   ├── main.tex
│   ├── preamble.tex
│   ├── chapters/
│   │   ├── ch01.tex   # Introdução
│   │   ├── ch02.tex   # Fundamentos teóricos
│   │   ├── ch03.tex   # Modelagem numérica
│   │   ├── ch04.tex   # Observações
│   │   ├── ch05.tex   # Métodos de assimilação
│   │   ├── ch06.tex   # Filtragem e variação
│   │   ├── ch07.tex   # Métodos híbridos
│   │   ├── ch08.tex   # Qualidade e erro
│   │   ├── ch09.tex   # HPC e automação
│   │   ├── ch10.tex   # Aplicações
│   │   └── ch11.tex   # Perspectivas futuras
│   ├── bib/
│   │   └── references.bib
│   ├── figures/
│   ├── tables/
│   └── glossary.tex
│
├── Makefile
├── README.md
├── LICENSE
└── .gitignore


````

## Compilação local
Requisitos: TeX Live completo, `biber`, `latexmk`.

```bash
cd src
latexmk -pdf -interaction=nonstopmode main.tex
# PDF gerado: src/main.pdf
````

## CI/CD

* **Build automático** do PDF em cada push (Actions → Build LaTeX PDF).
* **GitHub Pages** com o PDF publicado em `/livro.pdf`.
* **Releases** geram um PDF anexado quando você cria uma tag (`vX.Y.Z`).

## Licença

Conteúdo sob **Creative Commons BY-NC 3.0** (uso não comercial com atribuição).
Consulte o arquivo `LICENSE`.

