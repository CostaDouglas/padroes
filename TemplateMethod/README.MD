O padrão do Template Method sugere que você quebre um algoritmo em uma série de etapas, transforme essas etapas em métodos, e coloque uma série de chamadas para esses métodos dentro de um único método padrão. As etapas podem ser tanto abstratas, ou ter alguma implementação padrão. Para usar o algoritmo, o cliente deve fornecer sua própria subclasse, implementar todas as etapas abstratas, e sobrescrever algumas das opcionais se necessário (mas não o próprio método padrão).

Intent:
Defina o esqueleto de um algoritmo em uma operação, adiando algumas etapas para as subclasses do cliente. O método de modelo permite que as subclasses redefinam certas etapas de um algoritmo sem alterar a estrutura do algoritmo.
A classe base declara 'marcadores de posição' do algoritmo e as classes derivadas implementam os marcadores de posição.

Estrutura:
A Classe Abstrata declara métodos que agem como etapas de um algoritmo, bem como o próprio método padrão que chama esses métodos em uma ordem específica. Os passos podem ser declarados como abstratos ou ter alguma implementação padrão.
As Classes Concretas podem sobrescrever todas as etapas, mas não o próprio método padrão.

Aplicabilidade:
Utilize o padrão Template Method quando você quer deixar os clientes estender apenas etapas particulares de um algoritmo, mas não todo o algoritmo e sua estrutura.
O Template Method permite que você transforme um algoritmo monolítico em uma série de etapas individuais que podem facilmente ser estendidas por subclasses enquanto ainda mantém intacta a estrutura definida em uma superclasse.
Utilize o padrão quando você tem várias classes que contém algoritmos quase idênticos com algumas diferenças menores. Como resultado, você pode querer modificar todas as classes quando o algoritmo muda.
Quando você transforma tal algoritmo em um Template Method, você também pode erguer as etapas com implementações similares para dentro de uma superclasse, eliminando duplicação de código. Códigos que variam entre subclasses podem permanecer dentro das subclasses.
