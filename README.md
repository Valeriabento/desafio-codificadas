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
