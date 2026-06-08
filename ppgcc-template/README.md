# Template PPGCC UFERSA/UERN — versão 2.0

Template LaTeX para dissertações e teses do **Programa de Pós-Graduação em
Ciência da Computação (PPGCC)** da UFERSA em associação ampla com a UERN.

Normas seguidas: **ABNT NBR 14724:2011**, **NBR 6023:2018**,
**NBR 10520:2023** e manual da Biblioteca UFERSA.

---

## Estrutura de arquivos

```
dissertacao.tex               ← arquivo principal (compile este)
Makefile                      ← script de compilação
lib/
  ppgcc.sty                   ← pacote de estilo (não edite)
  UFERSA.png                  ← logo UFERSA
  UERN.png                    ← logo UERN
pre-textuais/
  dedicatoria.tex
  agradecimentos.tex
  epigrafe.tex
  resumo.tex
  abstract.tex
  abreviaturas.tex
  errata.tex                  ← descomente em dissertacao.tex se necessário
capitulos/
  1-introducao.tex
  2-fundamentacao-teorica.tex
  3-trabalhos-relacionados.tex
  4-metodologia.tex
  5-desenvolvimento.tex
  6-avaliacao.tex
  7-conclusao.tex
pos-textuais/
  referencias.bib             ← BibTeX
  apendices/
    apendice-a.tex
  anexos/
    anexo-a.tex
figuras/                      ← coloque suas imagens aqui
```

---

## Como compilar

### Via Makefile (recomendado)
```bash
make          # compilação completa (pdflatex → bibtex → pdflatex × 2)
make quick    # compilação rápida (sem referências atualizadas)
make clean    # remove arquivos auxiliares
make cleanall # remove auxiliares + PDF
```

### Manualmente
```bash
pdflatex dissertacao
bibtex dissertacao
pdflatex dissertacao
pdflatex dissertacao
```

### Via Overleaf
1. Compacte toda a pasta em `.zip`
2. Faça upload no Overleaf (New Project → Upload)
3. Defina `dissertacao.tex` como documento principal
4. Compile (o Overleaf usa latexmk automaticamente)

---

## Como personalizar

### 1. Preencha os metadados no topo de `dissertacao.tex`

```latex
\ppgccTipoTrabalho{dissertacao}   % ou tese
\ppgccEhQualificacao{nao}         % sim durante a qualificação
\titulo{Meu Título}
\autor{Meu Nome}
\ppgccOrientador{Prof. Dr. Meu Orientador}
% etc.
```

### 2. Edite os capítulos em `capitulos/`

Crie novos arquivos `.tex` para cada capítulo e adicione
`\input{capitulos/meu-capitulo}` em `dissertacao.tex`.

### 3. Adicione referências em `pos-textuais/referencias.bib`

Use os exemplos no arquivo como guia. Ferramentas úteis:
- [Zotero](https://www.zotero.org/) com exportação BibTeX
- [JabRef](https://www.jabref.org/)
- [Google Scholar](https://scholar.google.com/) → Citar → BibTeX

### 4. Figuras

Coloque os arquivos (`.pdf`, `.png`, `.jpg`) na pasta `figuras/`.
Referencie sem extensão:

```latex
\includegraphics[width=0.8\textwidth]{figuras/minha-figura}
```

### 5. Ficha catalográfica

Solicite à Biblioteca da UFERSA. Quando receber o PDF:
1. Salve como `pre-textuais/ficha-catalografica.pdf`
2. Descomente o bloco correspondente em `dissertacao.tex`

---

## Formatação ABNT resumida

| Elemento | Especificação |
|---|---|
| Papel | A4 (21 × 29,7 cm) |
| Margens | Sup 3 cm · Inf 2 cm · Esq 3 cm · Dir 2 cm |
| Fonte | Arial ou Times New Roman 12 pt |
| Espaçamento | 1,5 no texto; simples em citações longas, notas, referências |
| Recuo de parágrafo | 1,25 cm |
| Numeração | Romanos nos pré-textuais (a partir da folha de rosto, contados mas não impressos); arábicos a partir da Introdução, canto superior direito |
| Capítulo | CAIXA ALTA, negrito, tamanho 12 |
| Seção | Negrito, tamanho 12 |
| Subseção | Negrito itálico, tamanho 12 |
| Subsubseção | Itálico, tamanho 12 |
| Legendas | Acima da figura/tabela; fonte abaixo |
| Citação direta > 3 linhas | Recuo 4 cm, fonte 11, espaço simples, sem aspas |

---

## Dúvidas sobre normas

Consulte a **Biblioteca Central Orlando Teixeira (BCOT-UFERSA)**:
https://ufersa.edu.br/biblioteca

---

## Histórico de versões

- **2.0 (2025)** — reescrito do zero, estrutura plana, corrigidos bugs
  da versão anterior, alinhado às normas ABNT vigentes
- **1.0 (~2015)** — versão original de Oton Crispim Braga
  (adaptada de template UFC/UECE)
