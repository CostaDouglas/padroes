      Pattern Name and Classification 
O Memento é um padrão de projeto comportamental que permite que você salve e restaure o estado anterior de um objeto sem revelar os detalhes de sua implementação.

      Intent/Motivation/Applicability 
O padrão Memento delega a criação dos retratos do estado para o próprio dono do estado, o objeto originador. Portanto, ao invés de outros objetos tentarem copiar o estado do editor “a partir do lado de fora”, a própria classe do editor pode fazer o retrato já que tem acesso total a seu próprio estado.

O padrão sugere armazenar a cópia do estado de um objeto em um objeto especial chamado memento. Os conteúdos de um memento não são acessíveis para qualquer outro objeto exceto aquele que o produziu. Outros objetos podem se comunicar com mementos usando uma interface limitada que pode permitir a recuperação dos metadados do retrato (data de criação, nome a operação efetuada, etc.), mas não ao estado do objeto original contido no retrato.

Tal regra restritiva permite que você armazene mementos dentro de outros objetos, geralmente chamados de cuidadores. Uma vez que o cuidador trabalha com o memento apenas por meio de uma interface limitada, ele não será capaz de mexer com o estado armazenado dentro do memento. Ao mesmo tempo, o originador tem acesso total a todos os campos dentro do memento, permitindo que ele o restaure ao seu estado anterior à vontade.

O Padrão Comportamental Memento possui uma grande gama de aplicações onde é necessário a recuperação de um estado anterior de um objeto como um todo, qualquer tipo de editor precisa oferecer uma maneira de desfazer ações como restaurar imagens, textos etc. Para isso, o padrão Memento procura recuperar o estado anterior dessas ações e copiar os mesmos para um objeto a ser restaurado. 

  
    Structure
![](https://refactoring.guru/images/patterns/diagrams/memento/structure1.png)

  Participants 
Três objetos estão envolvidos na implementação do padrão Memento.

  Originador:
É o objeto cujo estado se deseja capturar.

  Memento:
Responsável por armazenar o estado interno do objeto Originador.

  Armazenador:
É o objeto que acessará o originador, e deseja desfazer qualquer mudança efetuada, caso necessário;
Ele é responsável por armazenar todos os Mementos;
Os Mementos devem ser recuperados de maneira LIFO (Last In First Out) onde o ultimo adicionado será o primeiro a ser recuperado.

    Example
O código em java ilustra a utilização do memento para desfazer ações de mudança de estado.
