# **Exercícios de Orientação a Objetos em Java**

## **Questões Teóricas sobre OO em Java**
1. O que é um objeto em Java?  
2. O que são classes e como elas se relacionam com objetos?  
3. Explique o conceito de encapsulamento e como ele é implementado em Java.  
4. O que é herança e qual a sua principal vantagem?  
5. O que significa a palavra-chave `super` em Java?  
6. Qual é a diferença entre **classe abstrata** e **interface**?  
7. Como funciona a sobrescrita de métodos (`@Override`) em Java?  
8. O que acontece se uma classe herdar duas interfaces que possuem métodos com o mesmo nome?  
9. Qual é a diferença entre **herança** e **composição**?  
10. Como evitar que uma classe seja herdada em Java?  

---

## **Exercícios de Herança em Java**

### **Exercício 1: Criando uma Hierarquia de Veículos**
Crie uma classe `Veiculo` com os seguintes atributos e métodos:
- `marca` (String)  
- `modelo` (String)  
- `ano` (int)  
- `exibirInfo()` (método que imprime os atributos)

Depois, crie duas classes que herdem de `Veiculo`:  
- `Carro` (com atributo `numeroPortas`)  
- `Moto` (com atributo `cilindradas`)  

Cada classe deve sobrescrever `exibirInfo()` para incluir suas informações adicionais.  

---

### **Exercício 2: Sistema de Funcionários**
Crie uma classe `Funcionario` com:
- `nome` (String)  
- `salario` (double)  
- Método `calcularBonus()`, que retorna 10% do salário.  

Agora, crie duas subclasses:
- `Gerente`, que tem um **bônus adicional de R$1000**.  
- `Estagiario`, que recebe **apenas 5% de bônus**.  

Crie um código que teste esses funcionários e exiba seus salários e bônus.

---

### **Exercício 3: Animais e Polimorfismo**
Crie uma classe base chamada `Animal` com:
- Método `emitirSom()`, que imprime `"Som genérico de animal"`.

Depois, crie as subclasses:
- `Cachorro`, que sobrescreve `emitirSom()` para imprimir `"Latido"`  
- `Gato`, que sobrescreve `emitirSom()` para imprimir `"Miau"`  

No `main()`, crie um array de `Animal` e armazene diferentes objetos (`Cachorro`, `Gato` etc.). Percorra o array e chame `emitirSom()` para cada um.
