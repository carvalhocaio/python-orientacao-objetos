# annotations

**O paradigma da Orientação à Objetos**  
A ideia central do paradigma da Orientação à Objetos é baseada em `Dado` e `Funcionalidade`(comportamentos) que andam juntos. Para que várias equipes consigam trabalhar em um mesmo projeto, é necessário que as responsabilidades de cada código estejam bem definidas e claras, evitando conflitos na hora de realizar mudanças e evoluções. Código com responsabilidade coesas é sinal de paradigma da Orientação à Objetos.

**Definindo uma classe**  
- Uma classe é uam especificação de um tipo, definindo valores e comportamentos
- Um objeto é uma instância de uma classe onde podemos definir valores para seus atributos
- Uma boa analogia é considerar a classe como a receita para a criação de algum prato.

## Construtores com valores padrão
Temos uma conta bancária **DevInvest** que geralmente é criada com o limite de mil reais.
O código de criação de 3 objetos do tipo `Conta` fica assim:

```text
conta1 = Conta(1, "Fulano", 0.0, 1000.0)
conta2 = Conta(2, "Beltrano", 0.0, 1000.0)
conta3 = Conta(3, "Sicrano", 0.0, 2000.0)
```

Como podemos fazer no Python para economizar a escrita do código de criação de um objeto `Conta`? Neste caso podemos supor que apenas **as contas com limites especias** precisariam passar tal argumento(no exemplo acima apenas `conta3` tem um limite especial). Isso é feito colocando na declaração da função construtora `__init__` um valor padrão para o limite.

Assim:

```python
class Conta:

    def __init__(self, numero, titular, saldo, limite = 1000.0):
        self.numero = numero
        self.titular = titular
        self.saldo = saldo
        self.limite = limite
```

E o código de nossos 3 objetos ficaria assim:
```text
conta1 = Conta(1, "Fulano", 0.0)
conta2 = Conta(2, "Beltrano", 0.0)
conta3 = Conta(3, "Sicrano", 0.0, 2000.0)
```

---

