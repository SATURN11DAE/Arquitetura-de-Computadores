# Estudo de Arquitetura de Computadores

Repositório pessoal com minhas anotações, resumos, resoluções de exercícios e experimentos sobre arquitetura e organização de computadores. O conteúdo é organizado por tema, não por livro, para que cada pasta funcione como um módulo independente de estudo.

O objetivo é consolidar o aprendizado de arquitetura de computadores de forma organizada, e fácil de consultar posteriormente. Além de praticar alguns conceitos com exercícios, cálculos de desempenho e pequenos experimentos em código verilog, assembly e c.

> Este repositório contém **apenas material autoral** (resumos com minhas palavras, código, exercícios resolvidos). Os PDFs dos livros **não** são versionados aqui por questões de direitos autorais.

---

## Referências principais

|Sigla|Livro|Autores|Foco|
|---|---|---|---|
|**COD**|_Computer Organization and Design: The Hardware/Software Interface_ (ARM Edition)|David A. Patterson, John L. Hennessy|Introdutório; organização do computador e interface hardware/software|
|**CA:AQA**|_Computer Architecture: A Quantitative Approach_ (6ª ed.)|John L. Hennessy, David A. Patterson|Avançado; análise quantitativa e decisões de projeto|

A ideia é usar o **COD** como base conceitual e o **CA:AQA** como aprofundamento quantitativo em cada tema.

---

## Estrutura do repositório

```text
Arquitetura-de-Computadores/
├── README.md                          ← onde estamos
├── 01-fundamentos-e-desempenho/       em andamento
│   └── README.md
├── 02-.../                            a definir conforme o avanço dos estudos
└── ...
```

### Módulos

|#|Pasta|Tema|Status|
|---|---|---|---|
|01|`01-fundamentos-e-desempenho`|Abstrações, tecnologia, desempenho, potência, custo e dependabilidade|🟡 Em andamento|
|02|`02-conjunto-de-instrucoes`|ISA, linguagem de montagem, ARM|⚪ Planejado|
|03|`03-aritmetica-computacional`|Representação numérica, ULA, ponto flutuante|⚪ Planejado|
|04|`04-processador-e-pipeline`|Caminho de dados, controle, pipeline, ILP|⚪ Planejado|
|05|`05-hierarquia-de-memoria`|Caches, memória virtual, otimizações|⚪ Planejado|
|06|`06-paralelismo`|DLP, TLP, multiprocessadores, GPUs|⚪ Planejado|
|07|`07-sistemas-em-larga-escala`|Warehouse-scale computers, arquiteturas de domínio específico|⚪ Planejado|

> A lista de módulos futuros é um roteiro inicial e pode mudar conforme eu avançar nos livros.

**Legenda:** ✅ concluído · 🟡 em andamento · ⚪ planejado

---

## Como cada módulo é organizado

Cada pasta segue, sempre que possível, o mesmo padrão:

```text
NN-nome-do-modulo/
├── README.md        # visão geral, mapeamento nos livros, conceitos e fórmulas
├── resumos/         # anotações por tópico (.md)
├── exercicios/      # resoluções comentadas
├── codigo/          # scripts e experimentos (Python, C, assembly...)
└── imagens/         # diagramas e figuras próprias
```

---

## Convenções

- **Idioma:** português, mantendo termos técnicos em inglês quando forem o padrão da área (ex.: _pipeline_, _cache_, _throughput_).
- **Fórmulas:** escritas em LaTeX, renderizadas pelo próprio GitHub (`$...$` e `$$...$$`).
- **Resumos:** sempre com minhas próprias palavras, indicando a seção do livro de origem.
- **Exercícios:** identificados pela numeração do livro (ex.: `CA:AQA 1.7`), com a resolução explicada passo a passo.

---

## Como usar

```bash
git clone https://github.com/<seu-usuario>/arquitetura-de-computadores.git
cd Arquitetura-de-Computadores
```

Comece pelo módulo `01-fundamentos-e-desempenho` e siga a numeração.

Para rodar os scripts de exemplo (quando houver), as dependências específicas ficam documentadas no README de cada módulo.

---

## Licença

Material autoral sob a licença MIT (código) e [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (textos). Os livros referenciados pertencem a seus respectivos autores e editoras.

---
