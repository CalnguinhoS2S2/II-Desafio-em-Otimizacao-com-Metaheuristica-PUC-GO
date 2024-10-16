## II Desafio em Otimizacao com Metaheuristica PUC GO
## Sumário
- [Equipe](#equipe)
- [Descrição do Hardware e Software Utilizados](#descrição-do-hardware-e-software-utilizados)
  - [Software](#software)
  - [Hardware](#hardware)
  - [Instâncias Utilizadas](#instâncias-utilizadas)
- [Descrição do Problema](#descrição-do-problema)
  - [Metaheurísticas Usadas](#metaheurísticas-Usadas)
    - [GRASP](#grasp)
    - [SA](#sa)
    - [VNS](#vns)

# Equipe
[![suehtaMFr](https://avatars.githubusercontent.com/u/104003912?size=100)](https://github.com/suehtaMFr)
[![CalnguinhoS2S2](https://avatars.githubusercontent.com/u/126282504?size=100)](https://github.com/CalnguinhoS2S2)

# Descrição do Hardware e Software Utilizados
## Software:
- *Visual Studio Code* foi utilizado.
- O algoritmo foi testado em um sistema operacional *Windows 11 Pro*.

## Hardware:
- *Processador:* AMD Ryzen 5 5600G.
- *Memória RAM:* 32 GB.
- *SSD:* 1 TB.

# Instâncias Utilizadas:
As principais instâncias utilizadas foram:
- *Falkenauer*.
- *Wäscher*.
- *Hard28*.

Retiradas do [BPPLib - A Bin Packing Problem Library](https://site.unibo.it/operations-research/en/research/bpplib-a-bin-packing-problem-library)

# Descrição do Problema:
O problema de empacotamento de Itens(BPP, do inglês Bin Packing Problem) é um problema clássico de otimização combinatória. O objetivo desse problema é empacotar um número de itens de diferentes tamanhos em um numero minimo de caixas ou "bins", respeitando a capacidade máxima de cada caixa, por ser um problema NP-difícil, que significa que não existe um algoritmo eficiente que garanta uma solução ótima para grande instâncias do problema. Contudo, há várias abortagens heurísticas que são frequentemente usadas na prática, como as *Metaheurísticas*.

# Metaheurísticas Testados:
As Metaheurísticas observadas para resolução desse problema foram *Greedy Randomized Adaptive Search Procedure(GRASP)*, *Simulated Annealing(SA)* e o *Variable Neighborhood Search(VNS)*.

  - *GRASP* 
    - Combina estratégias gulosas e elementos de aleatoridade para explorar o espaço de soluções de maneira eficaz, o *GRASP* tem duas etapas principais:
        1. *Fase de Construção:*
          -  Constroi uma solução inicial de forma gulosa, ou seja, selecionando de forma iterativa componentes que minimizam(ou maximizam) a função objetivo.
        
        2. *Fase de busca local:*
          - O algoritmo faz uma busca local para melhorar a solução construida inicialmente, onde a busca local tenta encontrar uma solução vizinha que tenha um valor melhor na função objetivo.
    - *Pseudocódigo*

      ![grasp](https://github.com/CalnguinhoS2S2/II-Desafio-em-Otimizacao-com-Metaheuristica-PUC-GO/blob/main/imagens/GRASPP.png)

  - *SA* 
    - Modelado para simular o recozimento de sólidos, onde adapta esse processo físico para resolver problemas de otimização, usando conceitos como:

      1. *Estado:* solucao do problema
      2. *Enengia:* qualidade da solução, valor da função objetivo a ser minimizada ou maximizada.
      3. *Temperatura:* parâmetro que controla a probabilidade de aceitar soluções piores durante a busca.
      4. *Função de Transição:* perturbação para geral novas soluções a partir da solução atual.
      5. *Critério de Aceitação:* define se uma solução vai ser aceita ou não, de acordo com a temperatura e energia atual.

      ![SA](https://github.com/CalnguinhoS2S2/II-Desafio-em-Otimizacao-com-Metaheuristica-PUC-GO/blob/main/imagens/SAA.png)

  - *VNS*
    - Trabalha com várias estruturas de vizinhanças e explora soluções entre essas vizinhanças, se uma vizinhança não gerar boas soluções, uma outra vizinhança com outra estrutura diferente pode ter gerar boas soluções. O *VNS* tem os seguintes passos:

      1. *Definir uma solução inicial:* inicializa uma solução inicial *s* de forma aleatoria ou com ajuda de uma heurística.
      2. *Estruturas de vizinhança:* define uma série de vizinhanças *Nk(s)*, onde *k* indica a posição da visinhança, e *s* é a solução atual. Maior *k*, mais distante a vizinhança está de *s*.
      3. *Agitação(Shaking):* cria uma pertubação para explorar novas áreas.
      4. *Busca Local:* envolve uma pequena otimização dentro da vizinhança definida
      5. *Movimento ou atualização:*
          - se nova solução for melhor que a melhor solução atual, entao melhor solução atual atualiza para nova solução, e o algoritmo reinicia com a menor vizinhança.
          - se não houver melhoria, o algoritmo aumenta o valor de *k*, expandindo a vizinhança e continuando a busca.
      6. *Critério de parada:* O algoritmo continua até que uma condição de parada seja atendida, como atingir um número máximo de iterações ou um limite de tempo.

      ![VNS](https://github.com/CalnguinhoS2S2/II-Desafio-em-Otimizacao-com-Metaheuristica-PUC-GO/blob/main/imagens/vnss.png)
