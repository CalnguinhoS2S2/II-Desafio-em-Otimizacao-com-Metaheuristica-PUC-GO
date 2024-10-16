# II Desafio em Otimizacao com Metaheuristica PUC GO
## Sumário
- [Equipe](#equipe)
- [Descrição do Hardware e Software Utilizados](#descrição-do-hardware-e-software-utilizados)
  - [Software](#software)
  - [Hardware](#hardware)
  - [Instâncias Utilizadas](#instancias-utilizadas)
- [Descrição do Problema](#descricao-do-problema)
  - [Metaheurísticas Testadas](#metaheuristicas-testadas)
    - [GRASP](#grasp)
    - [SA](#sa)
    - [VNS](#vns)

# Equipe - Operação Impossivel : Protocolo Gambiarra
[![suehtaMFr](https://avatars.githubusercontent.com/u/104003912?size=100)](https://github.com/suehtaMFr)
[![CalnguinhoS2S2](https://avatars.githubusercontent.com/u/126282504?size=100)](https://github.com/CalnguinhoS2S2)
![imagem](https://github.com/CalnguinhoS2S2/II-Desafio-em-Otimizacao-com-Metaheuristica-PUC-GO/blob/main/imagens/foto.jpg)

# Descrição do Hardware e Software Utilizados
## Software:
- *Visual Studio Code* foi utilizado.
- O algoritmo foi testado em um sistema operacional *Windows 11 Pro*.

## Hardware:
- *Processador:* Intel i5-6200U.
- *Memória RAM:* 8 GB.
- *HD:* 1 TB.

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

# Instâncias Utilizadas:
As principais instâncias utilizadas foram:
- *Iori* - 601 itens.
- *School at al* - 50 itens.
- *Instâncias Aleatorias"* - 300.
- *Instances_with_solution* - 1000 and 5245 itens.                                                    
Retiradas do [Repositorio do Desafio](https://drive.google.com/drive/folders/1qelSSRXSk_9MVkEyxTo1Ag3Zj1vdffcH).

- *Instances_with_solution* - 1000 and 5245 itens.    
E a Instances_with_solution [Drive](https://drive.google.com/file/d/118M0_fHnSQqAShxjJ72aGq_yhZsHwvlr/view?usp=sharing)

# Meta-Heuristica Utilizadas
Das 3 metaheurísticas faladas, nós usamos apenas 2, *VNS* e o *GRASP*. Após uma análise comparativa dos algoritmos, constatou-se que o *SA*, embora eficiente em diversos cenários de otimização, não está proporcionando um desempenho adequado para este problema específico. O tempo de execução do *SA* foi consistentemente mais elevado, o que compromete a eficiência global da solução, especialmente em instâncias maiores e mais complexas. Além disso, os resultados finais de qualidade de solução foram inferiores quando comparados aos alcançados pelos algoritmos *GRASP* e *VNS*, que mostraram-se mais robustos e eficientes tanto em termos de tempo quanto de qualidade de soluções.

# Resultados
resposta 600_20000_DI_31 <br>
Grasp: <br>
tempo : 7.5 s <br>
resposta: 201

VNS: <br>
tempo: 0.3 s <br>
resposta: 199 <br>

resposta BPP_300_75_0.2_0.8_6<br>
Grasp: <br>
tempo: 2.8 s<br>
resposta: 161<br>

VNS:<br>
tempo: 0.1 s<br>
resposta: 155<br>

resposta N1W4B1R7<br>
Grasp: <br>
tempo: 0.1 s<br>
resposta: 6<br>

VNS:<br>
tempo: 0.1 s<br>
resposta: 6 <br>

resposta Instances_with_solution teste 8<br>
Resposta esperada = 406 <br>
Grasp: <br>
tempo: 21.6<br>
resposta: 424<br>

VNS:<br>
tempo: 0.3 s<br>
resposta: 411<br>

resposta Instances_with_solution teste 9<br>
Resposta esperada = 2099<br>
Grasp: <br>
tempo: 11m 10 s<br>
resposta: 2206<br>

VNS:<br>
tempo: 4.4 s<br>
resposta: 2132<br>

# Motificações feitas nos algoritmos

## *VNS*
Parâmetros
  - max_iterations: quantidade maxima que o codigo será rodada 

Modificação
    Escolha da vizinhança: Seleciona-se uma vizinhança específica, começando pelas mais próximas da solução atual.
    Perturbação aleatória: Modifica-se aleatoriamente a solução atual dentro da vizinhança escolhida, buscando escapar de mínimos locais.
    Busca local: A nova solução é refinada com uma busca local para tentar melhorá-la.
    Atualização: Se a nova solução é melhor, ela se torna a solução atual; caso contrário, aumenta-se a vizinhança e o processo continua.

Ordem de Funcionamento do Algoritmo *VNS*
  1. Definição da Solução Inicial: O algoritmo começa com uma solução inicial que pode ser gerada aleatoriamente ou a partir de uma heurística específica.

  2. Escolha da Estrutura de Vizinhança: Uma vizinhança é selecionada de um conjunto de estruturas de vizinhança predefinidas. A escolha começa com vizinhanças menores, que envolvem pequenas perturbações da solução atual.

  3. Perturbação da Solução Atual: A solução atual é perturbada dentro da vizinhança escolhida, alterando-a de forma aleatória para explorar novas áreas do espaço de busca.

  4 Busca Local na Nova Solução: Após a perturbação, a solução modificada passa por uma busca local, onde o algoritmo tenta encontrar melhorias dentro da vizinhança imediata da nova solução.

  5. Atualização da Solução: Se a nova solução é melhor que a atual, ela substitui a solução anterior e o algoritmo retorna à primeira vizinhança. Caso contrário, o algoritmo aumenta a vizinhança para explorar áreas mais distantes.

## *GRASP*
Parâmetros
  - max_iterations: quantidade maxima que o codigo será rodada

Modificação
    Buscal local: Seleciona uma caixa aleatoria e um item aleatorio dessa caixa e passa por todas as caixas e tenta colocar esse item em uma caixa, se a caixa que foi selecionada aleatoriamente ficar vazia, ela é removida da lista de caixas, enquanto houver como trocar tirar os itens de uma caixa o loop continua rodando.

Ordem de Funcionamento do Algoritmo *GRASP*
  1. Define uma Solução Gulosa: o algoritmo monta as caixas de acordo com a soma dos itens para não passar da capacidade, se passar uma nova caixa é criada e esse item é colocado dentro dela

  2. Busca Local: otimiza a solução gulosa, pegando uma caixa aleatoria e um item dentro dessa caixa e tentando colocar ele em outra caixa, com o intuito de esvaziar essa caixa aleatoria

  3. Atualização da solução: se a solução da busca local for melhor que a melhor solução atual, atualiza a melhor solução atual recebe solução da busca local
