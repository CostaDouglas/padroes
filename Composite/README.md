Composite é um padrão de projeto de software utilizado para representar um objeto formado pela composição de objetos similares. Este conjunto de objetos pressupõe uma mesma hierarquia de classes a que ele pertence. Tal padrão é, normalmente, utilizado para representar listas recorrentes - ou recursivas - de elementos. Além disso, este modo de representação hierárquica de classes permite que os elementos contidos em um objeto composto sejam tratados como se fossem um objeto único. Desta forma, os métodos comuns às classes podem ser aplicados, também, ao conjunto agrupado no objeto composto.
As classes e objetos participantes nesse padrão são:

        Componente
    Declara a interface para objetos nessa composição.
    Implementa o comportamento padrão para a interface comum à todas as classes.
    Declara uma interface para acessar os componentes-filho.
    (Opcional) - Define uma interface para acessar os componentes-pai na estrutura recursiva, e a implementa se for apropriado.
        Folha
    Representa o objeto folha na composição. A folha não tem nenhum componente-filho.
    Define o comportamento para objetos primitivos na composição.
    Herda todos os métodos de Component porém só implementa de fato os que lhe interessam,neste caso o método Operation, nos outros são inseridos exceções que serão geradas
    em tempo de execução.
       Composite
    Define o comportamento para componentes que possuam componentes-filho.
    Armazena componentes-filho.
    Implementa funções relacionadas aos componentes-filho na interface do Componente.
        Cliente
    Manipula objetos da composição através da interface do Componente.
