# Teorias
- Objetivo: Estudar princípios da programação orientada a objetos (SOLID), Código Limpo, API Rest dentre outros.

- <a href="https://medium.com/desenvolvendo-com-paixao/o-que-%C3%A9-solid-o-guia-completo-para-voc%C3%AA-entender-os-5-princ%C3%ADpios-da-poo-2b937b3fc530">Retirado de </a>


# SOLID: Princípios da programação orientada a objetos 
### O que é SOLID? 
SOLID é um acrônimo criado por Michael Feathers após observar que cinco princípios da orientação a objetos e design de código, criados por Robert C, Marking ( Uncle Bob) e abordados no artigo THe Principlees of OOD. 


SOLID: Os 5 princípios da POO 
1. **S** - Single Responsability Principle (Princípio da responsabilidade única)
2. **O** - Open-Closed Principle - Principle Aberto - Fechado 
3. **L** - Liskov Substitutiion Principle ( Princípio da substituição de Liskov )
4. **I** - Interface Segregation Principle - Principío da Segregação da Interface 
5. **D** - Dependency Inversion Principle - Princípio da inversão da dependência 

Esses princípios ajudam o programador a escrever códigos mais limpos, separando responsabilidades, diminuindo acoplamentos, facilitando na refatoração e estimulando o reaproveitamento do código.


# 1. SRP — Single Responsibility Principle:
**Princípio da Responsabilidade Única** — Uma classe deve ter um, e **somente um, motivo para mudar**.

Esse princípio declara que **uma classe deve ser especializada em um único assunto** e **possuir apenas uma responsabilidade dentro do software**, ou seja, a classe deve ter uma **única tarefa ou ação para executar**.

Quando estamos aprendendo programação orientada a objetos, sem sabermos, damos a uma classe mais de uma responsabilidade e acabamos criando classes que fazem de tudo — God Class*. Num primeiro momento isso pode parecer eficiente, mas como as responsabilidades acabam se misturando, quando há necessidade de realizar alterações nessa classe, será difícil modificar uma dessas responsabilidades sem comprometer as outras. Toda alteração acaba sendo introduzida com um certo nível de incerteza em nosso sistema — principalmente se não existirem testes automatizados!

*God Class — Classe Deus: Na programação orientada a objetos, é uma classe que sabe demais ou faz demais.

```
class Order
{
    public function calculateTotalSum(){/*...*/}
    public function getItems(){/*...*/}
    public function getItemCount(){/*...*/}
    public function addItem($item){/*...*/}
    public function deleteItem($item){/*...*/}
}

class OrderRepository
{
    public function load($orderID){/*...*/}
    public function save($order){/*...*/}
    public function update($order){/*...*/}
    public function delete($order){/*...*/}
}

class OrderViewer
{
    public function printOrder($order){/*...*/}
    public function showOrder($order){/*...*/}
}
```


O princípio da responsabilidade única não se limita somente a classes, ele também pode ser aplicado em métodos e funções, ou seja, tudo que é responsável por executar uma ação, deve ser responsável por apenas aquilo que se propõe a fazer.

# 2. OCP — Open-Closed Principle:
Princípio Aberto-Fechado — Objetos ou entidades devem estar abertos para extensão, mas fechados para modificação, ou seja, quando novos comportamentos e recursos precisam ser adicionados no software, devemos estender e não alterar o código fonte original.