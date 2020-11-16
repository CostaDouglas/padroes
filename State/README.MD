      Pattern Name and Classification
O State é um padrão de projeto comportamental que permite que um objeto altere seu comportamento quando seu estado interno muda. Parece como se o objeto mudasse de classe.

      Intent/Motivation/Applicability 
O padrão State é intimamente relacionado com o conceito de uma Máquina de Estado Finito.A ideia principal é que, em qualquer dado momento, há um número finito de estados que um programa possa estar. Dentro de qualquer estado único, o programa se comporta de forma diferente, e o programa pode ser trocado de um estado para outro instantaneamente.
Contudo, dependendo do estado atual, o programa pode ou não trocar para outros estados. Essas regras de troca, chamadas transições, também são finitas e pré determinadas.

O padrão State sugere que você crie novas classes para todos os estados possíveis de um objeto e extraia todos os comportamentos específicos de estados para dentro dessas classes.

Ao invés de implementar todos os comportamentos por conta própria, o objeto original, chamado contexto, armazena uma referência para um dos objetos de estado que representa seu estado atual, e delega todo o trabalho relacionado aos estados para aquele objeto.

Para fazer a transição do contexto para outro estado, substitua o objeto do estado ativo por outro objeto que represente o novo estado. Isso é possível somente se todas as classes de estado seguirem a mesma interface e o próprio contexto funcione com esses objetos através daquela interface.

Essa estrutura pode ser parecida com o padrão Strategy, mas há uma diferença chave. No padrão State, os estados em particular podem estar cientes de cada um e iniciar transições de um estado para outro, enquanto que estratégias quase nunca sabem sobre as outras estratégias.

 -> Utilize o padrão State quando você tem um objeto que se comporta de maneira diferente dependendo do seu estado atual, quando o número de estados é enorme, e quando o código estado específico muda com frequência.
   
   O padrão sugere que você extraia todo o código estado específico para um conjunto de classes distintas. Como resultado, você pode adicionar novos estados ou mudar os existentes independentemente uns dos outros, reduzindo o custo da manutenção.

 -> Utilize o padrão quando você tem uma classe populada com condicionais gigantes que alteram como a classe se comporta de acordo com os valores atuais dos campos da classe.
  
  O padrão State permite que você extraia ramificações dessas condicionais para dentro de métodos de classes correspondentes. Ao fazer isso, você também limpa para fora da classe principal os campos temporários e os métodos auxiliares envolvidos no código estado específico.

 -> Utilize o State quando você tem muito código duplicado em muitos estados parecidos e transições de uma máquina de estado baseada em condições.
  
  O padrão State permite que você componha hierarquias de classes estado e reduza a duplicação ao extrair código comum para dentro de classes abstratas base.
  
    Structure
![](https://refactoring.guru/images/patterns/diagrams/state/structure-pt-br.png)

    Participants
  
Contexto: Este integrante define a interface com o cliente. Mantém uma instância de Estado Concreto que define seu estado atual.

Estado: Define uma interface para encapsular as responsabilidades associadas a um estado particular de contexto.

Subclasse EstadoConcreto: Cada uma dessas subclasses implementa o comportamento ou responsabilidade de Contexto.

    Example
O exemplo em python ilustra a estrutura do padrão de projeto State.
