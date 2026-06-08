# # Desafio Codeforces — Mentoria Codificadas | Além do Código
 
## Sobre este repositório
 
Este repositório contém minha resolução para o desafio de programação proposto na mentoria, utilizando problemas da plataforma [Codeforces](https://codeforces.com/) com auxílio de Inteligência Artificial.
 
---
 
## Problemas escolhidos
 
| # | Nome do problema | Link | Dificuldade |
|---|-----------------|------|-------------|
| 1 | A1. Lost Civilization (Easy Version) (Civilização Perdida — Versão Fácil) | [Ver no Codeforces](https://codeforces.com/problemset/problem/2201/A1) | 1300 |
 
---
 
## Problema 1 — A1. Lost Civilization (Easy Version) (Civilização Perdida — Versão Fácil)
 
### O que o problema pede?

O problema apresenta uma sequência final de números e pede para descobrir o menor tamanho possível da sequência inicial que poderia gerá-la. O algoritmo utilizado funciona inserindo elementos consecutivos (o valor $X + 1$ imediatamente após o valor $X$). 

Precisamos "reverter" esse processo e descobrir a quantidade mínima de blocos originais necessários para formar a sequência final dada. Se um número não for o sucessor direto do anterior (como pular de 1 para 3), ele obrigatoriamente fará parte de um novo bloco inicial.
 
 
### Como eu resolvi?

Eu li a lista de números do começo ao fim e fui comparando cada número com o anterior.

A lógica é simples: se o número atual for exatamente o anterior mais um (como um 3 depois de um 2), significa que o algoritmo conseguiu gerar ele ali na hora. Mas, se essa sequência quebrar (como aparecer um 5 depois de um 2), significa que o algoritmo não conseguiria fazer isso sozinho, logo, um novo bloco teve que começar ali.

No final, comecei contando o primeiro número como 1 bloco e fui somando mais 1 toda vez que essa sequência de "um em um" quebrava. O total de blocos encontrados é a resposta do problema.
 
 
### Código
```python
import sys
input = sys.stdin.readline  # Deixa a leitura do input muito mais rápida

t = int(input())
for _ in range(t):
    n = int(input())
    a = list(map(int, input().split()))
    count = 1
    for i in range(1, n):
        if a[i] != a[i-1] + 1:
            count += 1
    print(count)
---
 
## IA utilizada
 
**Qual IA você usou?**
Gemini.
 
**Como a IA te ajudou?**
Eu usei a IA principalmente para traduzir e desenrolar o enunciado do problema, que estava todo em inglês e parecia um pouco confuso de primeira. Ela me explicou de um jeito bem simples como o algoritmo funcionava na prática.

A partir dessa explicação, a IA me ajudou a clarear a mente e sugeriu a estratégia de mapear onde a sequência de números quebrava. Ela também me mostrou uma estrutura inicial de código em Python, que eu acabei adaptando e simplificando para deixar a lógica do meu jeito.
 
---
 
## Reflexão
 
### Dificuldades encontradas
A minha maior dificuldade ainda é na hora de desenvolver o código. Mesmo este sendo um problema considerado de nível fácil, eu ainda sinto bastante travamento e dificuldade para transformar a lógica que está na minha cabeça em linhas de código reais em Python. Além disso, o Codeforces foi uma novidade completa; como foi o meu primeiro contato com a plataforma, entender a dinâmica de leitura de dados e o formato dos desafios foi um processo bem desafiador.
 
 
### O que aprendi
O maior ganho desse desafio foi a experiência com as ferramentas, principalmente através da mentoria. Eu já conhecia o GitHub, mas o suporte da mentoria foi a parte que mais gostei, porque a explicação de como usá-lo na prática foi excelente e me deu muito mais segurança. Também aprendi a conhecer o Codeforces e o universo das maratonas de programação. Na parte técnica, aprendi a analisar sequências de dados e encontrar padrões lógicos simples — como a quebra de blocos — para resolver um problema que parecia complexo à primeira vista.
 
 
### Como foi a experiência?
Gostei de usar a IA como apoio para compreender o problema e estruturar a solução. Foi uma experiência produtiva, pois consegui focar na lógica sem perder tempo com a tradução ou interpretação do enunciado.
