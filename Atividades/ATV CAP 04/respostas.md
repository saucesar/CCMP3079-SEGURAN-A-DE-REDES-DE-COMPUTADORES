# Atividade Cap. 04 - Conceitos básicos de Teoria dos Números e Corpos Finitos
_______________________________

1. **Defina resumidamente, um grupo, um anel, um corpo.**

**Grupo**: Um grupo é uma estrutura algébrica composta por um conjunto não vazio de elementos, juntamente com uma operação binária (geralmente denotada por * ou multiplicação) que combina dois elementos do grupo para produzir um terceiro elemento. Para ser considerado um grupo, a operação binária deve satisfazer os seguintes axiomas: _Fechamento_, _Associatividade_, _Identidade_ e _Inverso_. Exemplo: conjunto dos números inteiros sob a operação de adição.

**Anel**: Estrutura algébrica com duas operações, uma de adição e outra de multiplicação, que satisfazem certas condições. O conjunto dos números inteiros Z com as operações usuais de adição e multiplicação constitui o protótipo de anel comutativo com identidade. Um anel é um terno (A, +, ·) em que (A, +) é um
grupo comutativo, (A, ·) é um semigrupo e em que a multiplicação é distributiva em relação à adição, isto é, para quaisquer a, b, c contidos em A.
**Corpo**: X é raiz do polinómio x^2 + 1 no corpo R[x]/(x^2 + 1), pois x^2 + 1 é a classe de x^2 + 1, ou seja, é o ideal (x^2 + 1), que é o zero do corpo quociente R[x]/(x^2 + 1). Sejam K um corpo, f(x) pertencente a K[x] e K* um corpo que é extensão de K. Dizemos que K* é corpo de ruptura de f(x) se f(x)
tem uma raiz em K*.

2. **O que significa dizer que b é um divisor de a?**

Significa que o número a pode ser dividido exatamente por b, ou seja, a divisão de a por b resulta em um quociente inteiro, sem deixar resto.

3. **Para cada uma das seguintes equações, encontre um inteiro x que satisfaça:**

(a) 5x ≡ 4 (mod 3)
(b) 7x ≡ 6 (mod 5)
(c) 9x ≡ 8 (mod 7)

**a**. 5x ≡ 4 (mod 3) => 5 * 2 ≡ 4 (mod 3) => 10 ≡ 4 (mod 3) => x = 2
**b**. 7x ≡ 6 (mod 5) => 7 * 3 ≡ 6 (mod 5) => 21 ≡ 6 (mod 5) => x = 3
**c**. 9x ≡ 8 (mod 7) => 9 * 4 ≡ 8 (mod 7) => 36 ≡ 8 (mod 7) => x = 4

4. **Encontre o inverso multiplicativo de cada elemento diferente de zero em Z5.**

De 1 em Z5 é 1, pois 1 * 1 ≡ 1 (mod 5).
De 2 em Z5 é 3, pois 2 * 3 ≡ 1 (mod 5).
De 3 em Z5 é 2, pois 3 * 2 ≡ 1 (mod 5).
De 4 em Z5 é 4, pois 4 * 4 ≡ 1 (mod 5).

5. **Determine os MDC:**

(a) mdc(24140, 16762). **Resposta 34**
(b) mdc(4655, 12075). **Resposta 35**

6. **Usando o algoritmo de Euclides estendido, encontre o inverso multiplicativo de:**

Feito no Sage

(a) 1234 mod 4321; **Resposta: divisor => 1, coeficiente a => -1082 coeficiente b => 309**
(b) 24140 mod 40902; **Resposta: divisor => 34, coeficiente a => -571 coeficiente b => 337**
(c) 550 mod 1769; **Resposta: divisor => 1, coeficiente a => 550 coeficiente b => -171**

7. **Determine o inverso multiplicativo de x3 + x + 1 em GF(24), com m(x) = x4 + x + 1.**

Feito no Sage

Inverso multiplicativo é  x^2 + 1.


8. Para a aritmética de polinômios com coeficientes em Z10, realize os seguintes cálculos:

Feito no Sage

(a) (7x + 2) − (x^2 + 5) = **−x^2 + 7x − 3**
(b) (6x^2 + x + 3) × (5x^2 + 2) = **x^2 + x + 1**


9. Estruture uma calculadora simples de quatro funções em GF(24). Você pode usar uma tabela
com valores pré-calculados para os inversos multiplicativos.