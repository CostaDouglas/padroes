O Adapter é um padrão de projeto estrutural que permite objetos com interfaces incompatíveis colaborarem entre si.

Problema:

Imagine que você está criando uma aplicação de monitoramento do mercado de ações da bolsa. A aplicação baixa os dados as ações de múltiplas fontes em formato XML e então mostra gráficos e diagramas maneiros para o usuário.
Em algum ponto, você decide melhorar a aplicação ao integrar uma biblioteca de análise de terceiros. Mas aqui está a pegadinha: a biblioteca só trabalha com dados em formato JSON.
Você não pode usar a biblioteca “como ela está” porque ela espera os dados em um formato que é incompatível com sua aplicação.
Você poderia mudar a biblioteca para que ela funcione com XML. Contudo, isso pode quebrar algum código existente que depende da biblioteca. E pior, você pode não ter acesso ao código fonte da biblioteca para começo de conversa, fazendo dessa abordagem uma tarefa impossível.

Solução 

Você pode criar um adaptador. Ele é um objeto especial que converte a interface de um objeto para que outro objeto possa entendê-lo.
Um adaptador encobre um dos objetos para esconder a complexidade da conversão acontecendo nos bastidores. O objeto encobrido nem fica ciente do adaptador. Por exemplo, você pode encobrir um objeto que opera em metros e quilômetros com um adaptador que converte todos os dados para unidades imperiais tais como pés e milhas.

Adaptadores podem não só converter dados em vários formatos, mas também podem ajudar objetos com diferentes interfaces a colaborar. Veja aqui como funciona:

    O adaptador obtém uma interface, compatível com um dos objetos existentes.
    Usando essa interface, o objeto existente pode chamar os métodos do adaptador com segurança.
    Ao receber a chamada, o adaptador passa o pedido para o segundo objeto, mas em um formato e ordem que o segundo objeto espera.

Estrutura e participantes:

Adaptador de objeto:

![](https://refactoring.guru/images/patterns/diagrams/adapter/structure-object-adapter.png)

1: O Cliente é uma classe que contém a lógica de negócio do programa existente.
2: A Interface do Cliente descreve um protocolo que outras classes devem seguir para ser capaz de colaborar com o código cliente.
3: O Serviço é alguma classe útil (geralmente de terceiros ou código legado). O cliente não pode usar essa classe diretamente porque ela tem uma interface incompatível.
4: O Adaptador é uma classe que é capaz de trabalhar tanto com o cliente quanto o serviço: ela implementa a interface do cliente enquanto encobre o objeto do serviço. O adaptador recebe chamadas do cliente através da interface do adaptador e as traduz em chamadas para o objeto encobrido do serviço em um formato que ele possa entender.
5: O código cliente não é acoplado à classe concreta do adaptador desde que ele trabalhe com o adaptador através da interface do cliente. Graças a isso, você pode introduzir novos tipos de adaptadores no programa sem quebrar o código cliente existente. Isso pode ser útil quando a interface de uma classe de serviço é mudada ou substituída: você pode apenas criar uma nova classe adaptador sem mudar o código cliente.

Adaptador de classe:

![](https://refactoring.guru/images/patterns/diagrams/adapter/structure-class-adapter.png)

1: A Classe Adaptador não precisa encobrir quaisquer objetos porque ela herda os comportamentos tanto do cliente como do serviço. A adaptação acontece dentro dos métodos sobrescritos. O adaptador resultante pode ser usado em lugar de uma classe cliente existente.

Exemplo

O exemplo simples mostra como um adaptador pode fazer com que objetos incompatíveis funcionem juntos.
