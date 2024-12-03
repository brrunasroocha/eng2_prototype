# Trabalho Final Engenharia de Softaware II

Trabalho final da disciplina sobre padrões de desenvolvimento. O padrão escolhido por mim foi o Prototype.

# Padrão de Desenvolvimento Prototype 

O padrão escolhido foi o Prototype, nele vimos que é um padrão de projeto criacional no qual os objetos são criados a partir de um protótipo. Esse padrão é útil para evitar o custo de criar objetos "do zero" e possibilita a clonagem de objetos já existentes, garantindo que suas propriedades e comportamentos sejam mantidos. A ideia central é fornecer um mecanismo para duplicar objetos, especialmente quando a criação direta é cara ou complexa.
Podemos utilizar o padrão quando a criação de novos objetos é custosa, seja em tempo ou recurso, é utilizado quando desejamos evitar dependência de subclasses para criar objetos e também quando o sistema precisa ser independente de como seus objetos são criados, compostos ou representados.

## Contexto prático

Este padrão é frequentemente usado em jogos, sistemas de configuração, editores de gráficos e outros aplicativos que demandam instâncias rápidas de objetos com características similares.

## Definição

É um padrão que especifica os tipos de objetos a serem criados usando uma instância prototípica como base, dando permissão a criação de novos objetos por meio da clonagem do protótipo.
É um padrão de projeto criacional que permite copiar objetos existentes sem fazer seu código ficar dependente de suas classes.

## Problemas

Imagine que você precisa criar uma cópia exata de um objeto. Como fazer isso? A abordagem inicial seria criar uma nova instância da mesma classe e copiar manualmente os valores de todos os campos do objeto original para o novo. Parece simples, mas há desafios envolvidos.
Primeiro, alguns objetos possuem campos privados, que não podem ser acessados diretamente fora da classe. Isso pode dificultar ou até impossibilitar a cópia desses valores.
Outro problema surge da necessidade de conhecer a classe específica do objeto para criar sua cópia. Isso torna seu código fortemente acoplado à classe, o que pode não ser ideal. Para complicar ainda mais, em muitos casos, você pode apenas trabalhar com a interface do objeto, sem saber qual é sua classe concreta. Esse cenário é comum em métodos que aceitam objetos baseados em uma interface genérica, sem revelar detalhes sobre sua implementação.


## Solução

O padrão Prototype permite que o próprio objeto se encarregue de sua clonagem, por meio de uma interface comum que declara um único método: clonar. Isso possibilita copiar objetos sem depender diretamente de suas classes.
O método de clonagem geralmente cria uma nova instância da mesma classe e copia todos os campos do objeto original, inclusive os privados, já que objetos da mesma classe podem acessar esses campos.
Esse padrão é útil quando você possui objetos com muitos campos ou configurações complexas. Em vez de criar um novo objeto do zero, basta clonar um protótipo pré-configurado, economizando tempo e esforço e evitando a necessidade de criar subclasses para cada variação.

## Estrutura do padrão Prototype

Prototype: Interface que declara o método clone.
ConcretePrototype: Implementa a interface e define como os objetos serão clonados.
Client: Utiliza o método clone para criar cópias do protótipo.

## Benfícios do Prototype

Reduz o custo de criação de objetos complexos.
Facilita a criação de objetos similares sem depender de sua classe concreta.
Permite copiar objetos sem se preocupar com a complexidade da construção.

## Desvantagens

A clonagem pode ser complicada quando o objeto possui referências circulares ou dados imutáveis.
Exige implementação cuidadosa para evitar erros no processo de cópia.

## Utilização do padrão nas APIs das linguagens de programação conhecidas
Pode ser utilizado em praticamente todas as linguagens de programação orientadas a objetos, adaptando-se às suas características. Ele é especialmente eficiente em linguagens dinâmicas, mas é igualmente aplicável em linguagens fortemente tipadas. A escolha da abordagem depende das necessidades do projeto e das ferramentas oferecidas pela linguagem.


# Conclusão Geral
O Prototype tem uma abordagem poderosa e versátil para criar objetos, especialmente em cenários onde a criação direta pode ser custosa ou complexa. Tem vários benefícios, dentre eles redução do custo de criação, é flexível, simples no gerenciamento de estados complexos e também reduz o acoplamento entre a classe cliente e as classes instanciadas. Pode ser aplicado em sistemas gráficos, sistemas distribuídos e em engenharia de softaware. Entretanto, ele possui alguns desafios e limitações. No entanto, sua aplicação deve ser avaliada cuidadosamente, considerando a complexidade do sistema e a natureza dos objetos que precisam ser clonados. Para sistemas modernos, o Prototype continua relevante, especialmente em linguagens que suportam ou facilitam essa abordagem.




