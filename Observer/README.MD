    Pattern Name and Classification

O Observer é um padrão de projeto comportamental que permite que você defina um mecanismo de assinatura para notificar múltiplos objetos sobre quaisquer eventos que aconteçam com o objeto que eles estão observando.

    Intent/Motivation/Applicability 

O padrão Observer funciona como assinaturas de jornais e revistas, ou seja, temos uma editora que publica as edições e pessoas que assinam os jornais ou revistas dessa editora e sempre recebem as novas edições assim que elas são publicadas. Enquanto a pessoa é assinante ela continua recebendo as edições na sua casa. Se a pessoa cancelar a assinatura do jornal ou da revista ela para de receber as edições.
O padrão Observer funciona da mesma forma, no entanto, tem-se que a editora (que publica) é o chamado SUBJECT no Padrão Observer e os assinantes (que recebem as novas publicações) são os chamados OBSERVER.
Os OBSERVERs registram-se no SUBJECT para receber atualizações quando os dados do SUBJECT são alterados. Os OBSERVERs também podem cancelar o seu registro e dessa forma não receber mais nenhuma atualização do SUBJECT.

O padrão Observer é muito utilizado em diversas APIs do Java e de outras plataformas também. Esse padrão é extremamente importante e útil devido aos seus inúmeros benefícios e boas práticas. Entre as boas práticas e princípios fundamentais que o padrão Observer nos proporciona temos: a separação dos aspectos que variam na aplicação, a programação para interface e não para uma implementação, prioridade à composição em relação a herança, interdependência entre os objetos, entre diversos outros.

    Structure 

![](https://refactoring.guru/images/patterns/diagrams/observer/example.png)

    Example

No exemplo, temos a implementação do Padrão de Projeto Observer utilizando a API do Java. Nota-se que a RevistaInformatica é o Subject que está aguardando registros de cliente. Assinante1 é um assinante que se registra na RevistaInformatica para receber notificações sempre que uma nova edição for publicada.
