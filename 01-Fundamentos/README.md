# 01. Fundamentos e Desempenho

Primeiro módulo do repositório. Cobre as bases da disciplina: abstrações de hardware e software, tendências tecnológicas, como medir e comparar desempenho, potência/energia, custo e dependabilidade.

---

## Material de origem

|Livro|Capítulo|Seções cobertas|
|---|---|---|
|**COD** (ARM Edition)|Cap. 1 · _Computer Abstractions and Technology_|1.1 – 1.13|
|**CA:AQA** (6ª ed.)|Cap. 1 · _Fundamentals of Quantitative Design and Analysis_|1.1 – 1.13 + Case Studies|

---

## Mapa de conteúdo: onde cada tema aparece

|Tema|COD (cap. 1)|CA:AQA (cap. 1)|
|---|---|---|
|Introdução e classes de computadores|1.1|1.1, 1.2|
|Grandes ideias da arquitetura|1.2 _Eight Great Ideas_|1.9 _Quantitative Principles_|
|Camadas de software e hardware|1.3 _Below Your Program_|n/d|
|Componentes de um computador|1.4 _Under the Covers_|1.3 _Defining Computer Architecture_|
|Tecnologia de processadores e memória|1.5|1.4 _Trends in Technology_|
|Desempenho|1.6|1.8 _Measuring, Reporting, and Summarizing Performance_|
|Potência e energia|1.7 _The Power Wall_|1.5 _Trends in Power and Energy_|
|Uniprocessador → multiprocessador|1.8 _The Sea Change_|1.2 (paralelismo)|
|Custo de fabricação|1.5 (_yield_, _wafer_)|1.6 _Trends in Cost_|
|Dependabilidade|n/d (apenas menções)|1.7 _Dependability_|
|Benchmarks reais|1.9 _Benchmarking the Intel Core i7_|1.8, 1.10|
|Estudo de caso: desempenho, preço e potência|n/d|1.10 _Putting It All Together_|
|Armadilhas comuns|1.10 _Fallacies and Pitfalls_|1.11 _Fallacies and Pitfalls_|

---

## Checklist de estudo

### COD, capítulo 1

- [ ] 1.1 Introdução: PCs, servidores, supercomputadores, embarcados, era pós-PC
- [ ] 1.2 As oito grandes ideias da arquitetura de computadores
- [ ] 1.3 Do programa ao hardware: compilador, montador, linguagem de máquina
- [ ] 1.4 Componentes: entrada/saída, caminho de dados, controle, memória, cache, ISA
- [ ] 1.5 Tecnologias: transistor, circuito integrado, _wafer_, _die_, _yield_
- [ ] 1.6 Desempenho: tempo de resposta, _throughput_, tempo de CPU, equação clássica
- [ ] 1.7 _Power Wall_: potência dinâmica e o fim do aumento de _clock_
- [ ] 1.8 A mudança para multiprocessadores
- [ ] 1.9 Benchmarks com Intel Core i7 (SPEC CPU)
- [ ] 1.10 Armadilhas e falácias
- [ ] 1.13 Exercícios

### CA:AQA, capítulo 1

- [ ] 1.1 Introdução e história do crescimento de desempenho
- [ ] 1.2 Classes de computadores e tipos de paralelismo (DLP, TLP, ILP, RLP; taxonomia de Flynn)
- [ ] 1.3 Definindo arquitetura: ISA, organização e hardware
- [ ] 1.4 Tendências: largura de banda × latência, escala de transistores e fios
- [ ] 1.5 Potência e energia em circuitos integrados
- [ ] 1.6 Custo: curva de aprendizado, _wafer_, _yield_, preço
- [ ] 1.7 Dependabilidade: MTTF, MTTR, disponibilidade
- [ ] 1.8 Medindo desempenho: SPEC, médias aritmética e geométrica
- [ ] 1.9 Princípios quantitativos: paralelismo, localidade, caso comum, Amdahl
- [ ] 1.10 Desempenho, preço e potência em servidores (SPECpower)
- [ ] 1.11 Falácias e armadilhas
- [ ] Estudos de caso e exercícios

---

## Conceitos-chave

### Oito grandes ideias (COD)

1. Projetar pensando na **Lei de Moore**
2. Usar **abstração** para simplificar o projeto
3. Tornar o **caso comum rápido**
4. Desempenho via **paralelismo**
5. Desempenho via _**pipelining**_
6. Desempenho via **predição**
7. **Hierarquia** de memórias
8. Dependabilidade via **redundância**

### Quatro princípios quantitativos (CA:AQA 1.9)

1. Aproveitar o **paralelismo**
2. **Princípio da localidade** (temporal e espacial)
3. Focar no **caso comum**
4. **Lei de Amdahl**

### Classes de computadores

|Classe|Prioridades típicas|
|---|---|
|Dispositivos móveis pessoais (PMD)|Custo, energia, tempo real, resposta|
|Desktop|Preço-desempenho, energia|
|Servidores|Disponibilidade, escalabilidade, _throughput_|
|_Clusters_ / _Warehouse-Scale Computers_|Preço-desempenho, proporcionalidade energética, disponibilidade|
|Embarcados / IoT|Custo, consumo, desempenho suficiente para a aplicação|

### Taxonomia de Flynn

`SISD` · `SIMD` · `MISD` · `MIMD`

---

## Fórmulas essenciais

### Desempenho relativo e _speedup_

$$ \frac{\text{Desempenho}_X}{\text{Desempenho}_Y} = \frac{\text{Tempo de execução}_Y}{\text{Tempo de execução}_X} = n $$

### Equação clássica de desempenho da CPU

$$ \text{Tempo de CPU} = \underbrace{\text{IC}}_{\text{nº de instruções}} \times \underbrace{\text{CPI}}_{\text{ciclos por instrução}} \times \underbrace{T_{clock}}_{\text{período do clock}} = \frac{\text{IC} \times \text{CPI}}{f_{clock}} $$

### Potência e energia dinâmicas (CMOS)

$$ E_{din} \propto \tfrac{1}{2} , C , V^2 \qquad\qquad P_{din} \propto \tfrac{1}{2} , C , V^2 , f $$

### Lei de Amdahl

$$ \text{Speedup}_{geral} = \frac{1}{(1 - f) + \dfrac{f}{s}} $$

onde $f$ é a fração do tempo que pode ser melhorada e $s$ é o ganho dessa parte.

### Custo de fabricação

$$ \text{Dies por wafer} \approx \frac{\pi ,(d_{wafer}/2)^2}{A_{die}} - \frac{\pi , d_{wafer}}{\sqrt{2 , A_{die}}} $$

$$ \text{Yield do die} = \text{Yield}_{wafer} \times \frac{1}{\left(1 + D \times A_{die}\right)^{N}} $$

com $D$ = densidade de defeitos e $N$ = fator de complexidade do processo.

### Dependabilidade

$$ \text{Disponibilidade} = \frac{\text{MTTF}}{\text{MTTF} + \text{MTTR}} \qquad \text{MTBF} = \text{MTTF} + \text{MTTR} $$

### Médias de desempenho

- **Média aritmética** para tempos de execução.
- **Média geométrica** para razões normalizadas (ex.: SPECratio).

---

## Armadilhas para lembrar

- Leis exponenciais sempre chegam ao fim (Lei de Moore, escala de Dennard).
- Multiprocessadores **não** são uma solução mágica.
- Cuidado com a Lei de Amdahl: otimizar uma fração pequena rende pouco.
- Melhorar desempenho **não** significa necessariamente melhorar eficiência energética.
- _Benchmarks_ envelhecem; desempenho de pico não reflete o desempenho observado.
- MTTF de disco anunciado não representa a vida útil de um disco individual.
- Um único ponto de falha derruba a dependabilidade de todo o sistema.

---

## Conteúdo da pasta

```text
01-fundamentos-e-desempenho/
├── README.md
├── resumos/
│   ├── 01-classes-de-computadores.md
│   ├── 02-oito-grandes-ideias.md
│   ├── 03-do-programa-ao-hardware.md
│   ├── 04-tendencias-tecnologicas.md
│   ├── 05-desempenho.md
│   ├── 06-potencia-e-energia.md
│   ├── 07-custo-e-yield.md
│   ├── 08-dependabilidade.md
│   ├── 09-benchmarks.md
│   └── 10-principios-quantitativos.md
├── exercicios/
│   ├── cod-cap1/
│   └── caaqa-cap1/
├── codigo/
│   ├── cpu_time.py
│   ├── amdahl.py
│   ├── die_yield.py
│   └── availability.py
└── imagens/
```

> Os arquivos acima serão criados conforme eu avançar. Os itens ainda não existentes aparecem como planejamento.

---

## Experimentos planejados

- [ ] Calculadora de **tempo de CPU** (IC × CPI × T) com comparação entre duas máquinas
- [ ] Gráfico da **Lei de Amdahl** para diferentes frações paralelizáveis
- [ ] Simulação de **yield × área do die** variando a densidade de defeitos
- [ ] Cálculo de **disponibilidade** para sistemas com e sem redundância
- [ ] Medir o tempo de um mesmo programa em C com `-O0`, `-O2` e `-O3` e relacionar com a equação de desempenho

---
