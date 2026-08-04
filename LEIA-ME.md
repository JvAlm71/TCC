# TCC — Modelo USPSC / ICMC (Engenharia de Computação)

Versão limpa do modelo oficial USPSC, já configurada para:

- **Unidade/tipo:** ICMC — TCC (`\siglaunidade{ICMC-TCC}`)
- **Curso:** Engenharia de Computação, português (`\programa{ECp}`)
- **Título:** "Avaliação da Experiência do Usuário do Aplicativo Trilha das
  Árvores usando métricas heurísticas e com estudo com usuários finais"

Os arquivos das outras unidades (EESC, IAU, IFSC, IQSC), dos outros modelos
(dissertação/tese, relatório) e o tutorial foram removidos para deixar só o
essencial.

---

## Arquivo que você compila

    USPSC-TCC-modelo-ICMCp.tex

É o único arquivo "raiz". Ele puxa todos os outros. **Compile sempre este.**

### Sequência de compilação (importante!)

Como usa referências no padrão ABNT (BibTeX), não basta compilar uma vez:

    pdflatex  USPSC-TCC-modelo-ICMCp
    bibtex    USPSC-TCC-modelo-ICMCp
    makeindex USPSC-TCC-modelo-ICMCp     (só se usar índice remissivo)
    pdflatex  USPSC-TCC-modelo-ICMCp
    pdflatex  USPSC-TCC-modelo-ICMCp

No **Overleaf** isso é automático: crie o projeto (upload deste .zip) e
defina `USPSC-TCC-modelo-ICMCp.tex` como documento principal. O Overleaf já
tem o abnTeX2 e todos os pacotes instalados.

---

## Onde mexer (na ordem)

1. **`USPSC-TCC-pre-textual-ICMC.tex`** — seus dados. Já contém o título.
   Falta preencher (procure por `>>>` no arquivo):
   - `\autor{}`, `\autorficha{}`, `\autorabr{}` — seu nome (3 formatos)
   - `\orientador{}` e afins — orientador(a); ajuste "Orientador:/Orientadora:"
   - `\data{}` — ano do depósito/defesa
   - `\cutter{}` — código fornecido pela Biblioteca com a ficha catalográfica

2. **`USPSC-TA-PreTextual/`** — elementos de abertura:
   - `USPSC-Resumo.tex` / `USPSC-Abstract.tex` — resumo e abstract + palavras-chave
   - `USPSC-Agradecimentos.tex`, `USPSC-Dedicatoria.tex`, `USPSC-Epigrafe.tex` (opcionais)
   - `USPSC-AbreviaturasSiglas.tex`, `USPSC-Simbolos.tex` (opcionais)

3. **`USPSC-TA-Textual/`** — o corpo do trabalho:
   - `USPSC-Cap1-Introducao.tex`
   - `USPSC-Cap2-Desenvolvimento.tex` (tem exemplo de tabela e figura para copiar)
   - `USPSC-Cap3-Conclusao.tex`
   - Para adicionar um capítulo: crie o `.tex` aqui e acrescente um
     `\include{USPSC-TA-Textual/nome-do-arquivo}` no arquivo principal, na
     seção "ELEMENTOS TEXTUAIS".

4. **`USPSC-bib/USPSC-modelo-references.bib`** — suas referências (formato BibTeX).
   No texto, cite com `\cite{chave}`. (O arquivo vem com várias entradas de
   exemplo do modelo original; pode apagá-las e colocar as suas.)

5. **`USPSC-TA-PosTextual/`** — apêndices, anexos e índice remissivo (opcionais).

---

## Ficha catalográfica e folha de aprovação

São PDFs em `USPSC-TA-PreTextual/`:

- `USPSC-fichacatalografica.pdf` — a Biblioteca do ICMC gera pra você; substitua
  este arquivo pelo definitivo quando tiver.
- `USPSC-folhadeaprovacao.pdf` — depois da defesa, coloque aqui o PDF da folha
  assinada pela banca.

Enquanto não tiver, o modelo compila com os PDFs de exemplo que já vêm.

---

## Não precisa mexer

- `USPSC-classe/` — o "motor" do modelo (classe, estilos de referência).
- `USPSC-unidades.tex` — mecanismo que carrega os dados do ICMC-TCC.
- `USPSC-img/` — imagens da capa e auxiliares.

---

## Idioma

Está tudo em português. Se um dia precisar da versão em inglês, o próprio
arquivo principal e o pré-textual têm comentários explicando quais linhas
comentar/descomentar (procure por "idioma" / "english").
