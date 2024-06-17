# DesafioControleFluxo
# Contador

Este é um programa simples em Java que solicita ao usuário dois parâmetros inteiros e imprime uma contagem de números com base na diferença entre esses parâmetros. O programa inclui uma validação que garante que o segundo parâmetro seja maior que o primeiro e lança uma exceção personalizada se essa condição não for atendida.

## Funcionalidades

- Solicita ao usuário dois parâmetros inteiros.
- Verifica se o segundo parâmetro é maior que o primeiro.
- Lança uma exceção personalizada se a condição não for satisfeita.
- Imprime a contagem de números entre os dois parâmetros fornecidos.

## Exceção Personalizada

O programa define uma exceção personalizada chamada `ParametrosInvalidosException` para tratar a situação onde o segundo parâmetro não é maior que o primeiro. A mensagem de erro é exibida ao usuário.

## Estrutura do Código

### Classe `ParametrosInvalidosException`

```java
class ParametrosInvalidosException extends Exception {
    public ParametrosInvalidosException(String mensagem) {
        super(mensagem);
    }
}

import java.util.Scanner;

public class Contador {
    public static void main(String[] args) {
        Scanner terminal = new Scanner(System.in);
        System.out.println("Digite o primeiro parâmetro");
        int parametroUm = terminal.nextInt();
        System.out.println("Digite o segundo parâmetro");
        int parametroDois = terminal.nextInt();

        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException exception) {
            System.out.println(exception.getMessage());
        }

        terminal.close();
    }

    static void contar(int parametroUm, int parametroDois) throws ParametrosInvalidosException {
        if (parametroUm >= parametroDois) {
            throw new ParametrosInvalidosException("O segundo parâmetro deve ser maior que o primeiro.");
        }

        int contagem = parametroDois - parametroUm;
        for (int i = 1; i <= contagem; i++) {
            System.out.println("Imprimindo número: " + i);
        }
    }
}
```
Como Executar
1.Certifique-se de ter o JDK instalado em seu sistema.
2.Compile o programa usando o seguinte comando no terminal:
javac Contador.java

3.Execute o programa com o comando:
java Contador

Exemplos de uso:
Digite o primeiro parâmetro
5
Digite o segundo parâmetro
10
Imprimindo número: 1
Imprimindo número: 2
Imprimindo número: 3
Imprimindo número: 4
Imprimindo número: 5


