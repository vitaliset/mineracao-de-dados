# Mineração de Dados 2020.QS

Neste repositório estou disponibilizando o **projeto** e as **listas** (com link para vídeos explicando as resoluções) realizados durante a disciplina [Mineração de Dados](http://professor.ufabc.edu.br/~thiago.covoes/mdqs_pos/). Esta disciplina foi disponibilizada de forma remota no quadrimestre suplementar de 2020 da UFABC ministrado pelo professor [**Thiago Covões**](http://professor.ufabc.edu.br/~thiago.covoes/). Recomendo fortemente as aulas ministradas pelo professor, que estão disponíveis nesta [playlist](https://www.youtube.com/playlist?list=PL8QzQjvH3N_MMuRKiyTCFyT20GKJplVSG).

## Alguns comentário sobre o projeto prático

No projeto (que fiz em dupla com meu amigo **Daniel Siqueira**), nos foi apresentado um projeto de consultoria sem escopo definido. Tínhamos disponível os dados históricos de visitas de clientes às lojas e quais carros foram observados pelos clientes. A ideia era pensar em uma solução que melhorasse o desempenho financeiro da loja.

Rapidamente tentamos formular o problema no framework de *inferência causal*:

- W (tratamento): variáveis do carro oferecido;
- X: variáveis do cliente;
- Y (outcome): cliente compra ou não o carro.  

No projeto estou usando uma técnica chamada __covariate adjustment  __(que funciona muito bem quando o tratamento é distribuído de forma independente dos valores de X). Nesta técnica, utilizamos a variável de tratamento como uma das variáveis explicativas do modelo e para inferir os diferentes outcomes potenciais (valores diferentes de Y, dado um tratamento escolhido).

A ideia prática do projeto é: dado um cliente novo que chega na loja, rodar o nosso algoritmo tentando prever a probabilidade de compra para cada um dos carros disponíveis em estoque na loja. Essa lista é fornecida ao vendedor que pode avaliar qual carro oferecer primeiro.

Aqui, um ponto de melhoria teria sido ser mais crítico ao procurar variáveis confundidoras. Assumimos que os carros eram oferecidos de maneira aleatória, oque fazia sentido no dataset artificial criado para o projeto, mas não se aplica a praticamente nenhum caso prático real de interesse. Em aplicações nesse contexto, técnicas de Doubly Robust ML costumam ser mais eficientes. Para mais detalhes vale conferir a biblioteca [CausalML](github.com/uber/causalml) da Uber.

____

PS1: Os notebooks têm os códigos que geram as imagens, mas o PDF com a lista era a forma final de envio. 

PS2: Não estou disponibilizando os dados que foram usados nas listas ou no projeto, mas fiquem a vontade para me contatar pelo [LinkedIn](https://www.linkedin.com/in/carlo-lemos/) caso estejam interessados nestes arquivos.

