# b_AI_atro

## Links interessantes:
- https://github.com/besteon/balatrobot

Uma opção seria usar esse balatrobot, que serve como uma interface para o jogo. Outra opção seria usar visão computacional, onde o a extração do que tá acontecendo no jogo vem do processamento do que está aparecendo NA TELA, dependendo das capacidades da primeira implementação, talvez seja necessário usar a segunda, que seria (um pouquinho) mais complicada, mas uma vez que foi implementada é só usar

Algorítmo:
- jogo começa, inicia o game loop
- 1: Jogar as cartas para bater a pontuação
  -  **Decisões:** Quais cartas jogar  
- 2: Após bater o blind, entramos na loja
  -  deve ser feita a estratégia de jogo (que seria importante ter uma noção do que pode ser comprado do jogo) para decidir o que vai ser comprado, ou não comprar nada para economizar dinheiro e aumentar interest.
  -  **Decisões:** Compras de carta
- 3. Então entramos no blind select, onde podemos pular os jogar ou pular os blinds (implementação dessa parte pode ser mais simples) 
 


# Noção geral do jogo:
## O Game Loop de Balatro: Poker, Power-ups e Progressão

O jogo é estruturado em uma série de rodadas chamadas *Anties* (Ante), onde o objetivo principal é acumular fichas (*Chips*) suficientes para vencer os *Blinds*.

O ciclo básico do jogo se divide em três etapas:

### 1. Rounds (Batalha e Pontuação)

Nesta etapa, você enfrenta o desafio de pontuação de um *Blind*.

* **Objetivo:** Alcançar a Pontuação de Fichas (*Target Chips*) exigida pelo *Blind* jogando mãos de Poker.
* **Mecânica de Jogo:**
    * Você começa com um número limitado de **Mãos** (jogadas) e **Descartes** (*Discards*) por rodada.
    * Você usa as cartas da sua mão para formar mãos de Poker (Par, Trinca, Full House, etc.).
    * **Cálculo de Pontuação:** Cada mão jogada gera pontos com base em dois fatores principais:
        $$\text{Pontuação Final} = (\text{Fichas da Mão} + \text{Fichas de Bônus}) \times \text{Multiplicador}$$
    * As **Fichas da Mão** vêm do valor base de cada tipo de mão (ex: Straight, Flush).
    * Os **Multiplicadores** vêm das cartas Coringas (*Jokers*), cartas Planetárias e efeitos de cartas especiais.
* **Resultado:** Se você atingir a pontuação alvo antes de esgotar suas Mãos/Descartes, você avança. Caso contrário, a partida termina (*Run Over*).

### 2. Shop (Oportunidade e Melhoria)

Após vencer um *Blind*, você acessa a Loja, o coração da progressão do seu *deck*.

* **Função:** Gastar o dinheiro que você ganhou para melhorar seu *deck* e ganhar bônus permanentes ou temporários.
* **Principais Itens na Loja:**
    * **Coringas (*Jokers*):** São o principal motor de poder do jogo. Eles fornecem bônus **passivos e permanentes** enquanto estão ativos. Eles podem adicionar Fichas de Bônus, aumentar Multiplicadores, ou fornecer efeitos únicos que interagem com o *deck* (ex: Coringa que multiplica o valor de todas as cartas de um naipe).
    * **Cartas Tarô (*Tarot Cards*):** Oferecem **modificações imediatas** ao seu *deck*. Você pode usá-las para aprimorar cartas (ex: transformar cartas em Wild, dar bônus de Multiplicador, mudar o naipe, ou destruir cartas para melhorar a consistência).
    * **Cartas Planetárias (*Planet Cards*):** Aumentam permanentemente o **nível** de um tipo específico de mão de Poker (ex: aumentar o nível do *Flush*). Isso eleva as Fichas e o Multiplicador base daquela mão, tornando-a mais poderosa.
    * **Packs de Reforço (*Booster Packs*):** Pacotes de cartas que adicionam novas cartas ao seu *deck*.
    * **Vouchers:** Bônus passivos permanentes que melhoram o seu *run* (ex: cartas mais raras na loja, descontos, mãos extras).
    * **Cartas Espectrais (*Spectral Cards*):** Oferecem efeitos poderosos e muitas vezes arriscados, como alterar drasticamente seu *deck* ou dar grandes quantidades de dinheiro.

### 3. Blind Select (Gerenciamento de Risco)

Antes de começar o próximo *Round*, você deve escolher qual dos três tipos de *Blind* (Cegos) você enfrentará.

* **Small Blind (Pequeno Cego):** O primeiro e mais fácil desafio.
* **Big Blind (Grande Cego):** O segundo e mais difícil desafio.
* **Boss Blind (Cego Chefe):** O desafio final de cada *Ante* (rodada maior).
* **Função do *Blind*:** Aumentar a dificuldade, exigindo uma pontuação de Fichas cada vez maior. O *Boss Blind* também adiciona uma **regra especial** que afeta a jogabilidade (ex: cartas de um certo naipe não contam para a pontuação, ou você não pode descartar certas cartas).

#### A Opção Chave: *Skip Blind* (Pular Cego)

A decisão estratégica mais importante é a opção de **Pular o *Blind***.

* Ao pular um *Blind* (Small, Big ou Boss), você não joga o *Round*, mas **recebe um bônus imediato** (dinheiro, um Coringa, etc.).
* **Risco e Recompensa:** Pular o *Blind* te dá um poder extra que pode ser vital para te preparar para desafios futuros, mas significa que você tem menos tempo para se preparar para o próximo *Blind*, cuja pontuação alvo será ainda mais alta.

O ciclo se repete até que você vença o *Boss Blind* do **Ante 8** para completar o jogo, ou até que você não consiga atingir a pontuação exigida, encerrando a partida.
