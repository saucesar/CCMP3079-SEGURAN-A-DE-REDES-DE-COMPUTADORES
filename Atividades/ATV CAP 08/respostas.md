# Atividade Cap. 08

1. **Por que mdc(n, n + 1) = 1 é para dois inteiros consecutivos n e n + 1?**

No contexto de dois inteiros consecutivos, suponha que temos dois inteiros consecutivos, n e n + 1. Isso significa que n + 1 é o próximo número após n. Agora, vamos pensar em quais são os possíveis divisores comuns desses dois números. Um divisor comum é um número inteiro que divide ambos os números.

Quando n é par, o próximo número n + 1 é ímpar. E quando n é ímpar, o próximo número n + 1 é par. Em ambos os casos, os números são diferentes em termos de paridade. Como um número par não pode ser divisível por um número ímpar (e vice-versa), não pode haver um divisor comum maior do que 1 entre n e n + 1.

Portanto, o MDC(n, n + 1) é igual a 1 para dois inteiros consecutivos porque eles não têm fatores primos em comum além do número 1. Isso ocorre porque eles são sempre diferentes em termos de paridade, e essa diferença impede que tenham divisores comuns maiores do que 1.

2. **Usando o teorema de Fermat, encontre $3^{201}$ mod 11.**

Aplicando o Teorema de Fermat:
$a = 3$
$p = 11$

$p-1 = 11 - 1 = 10$

Agora, aplicando o teorema:

$3^{10} ≡ 1 \mod (11)$

Isso significa que qualquer potência de 3 que seja múltiplo de 10 será congruente a 1 módulo 11.

Agora, queremos calcular $3^{201} mod 11No seu caso, você deseja calcular 3^201 mod 11 usando o Teorema de Fermat.

Primeiro, vamos verificar se 11 é um número primo. De fato, 11 é um número primo.

Agora, aplicando o Teorema de Fermat:
a = 3
p = 11

O valor de p-1 é 11 - 1 = 10.

Agora, aplicando o teorema:

3^(10) ≡ 1 (mod 11)

Isso significa que qualquer potência de 3 que seja múltiplo de 10 será congruente a 1 módulo 11.

Agora, queremos calcular $3^{201} \mod(11)$. Podemos fazer isso observando o padrão nas potências de 3 módulo 11:

$3^1 \mod(11) = 3$
$3^2 \mod(11) = 9$
$3^3 \mod(11) = 5$
$3^4 \mod(11) = 4$
$3^5 \mod(11) = 1$
$3^6 \mod(11) = 3$
...

O padrão se repete a cada 5 potências de 3. Portanto, podemos calcular 3^201 mod 11 encontrando o resto da divisão de 201 por 5, que é 1:

$3^{201} \mod(11) = 3^1 \mod(11) = 3$

Portanto, de acordo com o Teorema de Fermat, $3^{201} \mod(11)$ é igual a 3.

3. **Use o teorema de Fermat para encontrar um número a entre 0 e 72, com a congruente a 9794 módulo 73.**

$a ≡ 9794 \mod(73)$
$a^{72} ≡ 1 \mod(73)$

Vamos verificar valores de "a" entre 0 e 72 para encontrar um que seja congruente a 9794 módulo 73:

$9794 ≡ a^{72} \mod(73)$
$9794 \mod(73) = 12 $

$ a=0, a^{72} \mod(73) = 0 $
$ a=1, a^{72} \mod(73) = 1 $
$ a=2, a^{72} \mod(73) = 1 $
$ a=3, a^{72} \mod(73) = 55 $
...
$ a=43, a^{72} \mod(73) = 13 $
$ a=44, a^{72}\mod(73) = 70 $
...
$ a=55, a^{72} \mod(73) = 65 $
$ a=56, a^{72} \mod(73) = 31 $
$ a=57, a^{72} \mod(73) = 12 $

Logo o "a" procurado é 57.

4. **Use o teorema de Euler para encontrar um número a entre 0 e 9, tal que a seja congruente a $7^{1000}$ módulo 10. (Observe que isso é o mesmo que o último dígito da expansão decimal de $7^{1000}$.)**

O Teorema de Euler generaliza o Pequeno Teorema de Fermat para situações em que o módulo não é necessariamente primo, mas o número e o módulo são coprimos (ou seja, não têm fatores primos em comum, exceto 1).

O Teorema de Euler afirma que, se "a" e "n" são inteiros positivos coprimos (isto é, mdc(a, n) = 1), então:

a^φ(n) ≡ 1 (mod n)

Onde φ(n) é a função totiente de Euler, que conta quantos inteiros positivos são coprimos com "n". Para números primos, φ(n) = n - 1.

Um número "a" entre 0 e 9 que seja congruente a $7^{1000}$ módulo 10, significa que você está procurando o último dígito da expansão decimal de $7^{1000}$.

Para usar o Teorema de Euler, precisamos verificar se "7" e "10" são coprimos. Como "7" e "10" não têm fatores primos em comum além de 1, eles são coprimos.

Agora, aplicando o Teorema de Euler:
$a = 7$
$n = 10$

$φ(10) = 10 * (1 - 1/2) * (1 - 1/5) = 4$

Agora, aplicando o teorema:

$7^4 ≡ 1 \mod(10)$

Isso significa que qualquer potência de 7 que seja um múltiplo de 4 será congruente a 1 módulo 10.

Agora, queremos encontrar o último dígito da expansão decimal de $7^{1000}$. Como 1000 é múltiplo de 4 (1000 = 4 * 250), podemos concluir que:

$7^{1000} ≡ 7^4 * 7^{4 * 249} ≡ 1 * (7^4)^{249} ≡ 1^{249} ≡ 1 \mod(10)$

Portanto, o último dígito da expansão decimal de $7^{1000}$ é 1. Consequentemente, um número "a" entre 0 e 9 que seja congruente a $7^{1000}$ módulo 10 é 1.

5. **Use o teorema de Euler para encontrar um número x entre 0 e 28, com $x^{85}$ congruente a 6 módulo 35 (Você não precisará usar qualquer pesquisa por força bruta).**

a^φ(n) ≡ 1 (mod n)

φ(n) é a função totiente de Euler, que conta quantos inteiros positivos são coprimos com "n".

Procurando um número "x" que satisfaça a congruência:

$x^{85} ≡ 6 \mod(35)$

Para usar o Teorema de Euler, precisamos verificar se "x" e "35" são coprimos. Vamos calcular a função totiente de Euler para 35:

φ(35) = 35 * (1 - 1/5) * (1 - 1/7) = 24

Agora, aplicando o Teorema de Euler:
a = x
n = 35

Agora, precisamos determinar qual é o valor de φ(35) que é congruente a 85 módulo 24. Isso nos ajudará a reduzir o expoente para um valor mais gerenciável:

85 ≡ 13 (mod 24)

Agora, aplicando o teorema:

$x^{13} ≡ 1 \mod 35$

Portanto, qualquer potência de "x" que seja um múltiplo de 13 será congruente a 1 módulo 35.

Agora, podemos tentar diferentes valores de "x" entre 0 e 28 para encontrar um que satisfaça a congruência:

$x^{85} ≡ 6 \mod 35$

Ao tentar diferentes valores de "x", encontramos que "x = 8" é uma solução:

$8^{85} ≡ 6 \mod 35$

Portanto, o número "x" entre 0 e 28, com $x^{85}$ congruente a 6 módulo 35, é 8.



6. **Observe, na Tabela 8.2, que φ(n) é par para n > 2. Isso é verdadeiro para todo n > 2. Dê um argumento conciso para explicar por que isso acontece.**

A afirmação de que φ(n) é par para n > 2 é verdadeira para todos os números inteiros maiores que 2 porque a função totiente de Euler φ(n) conta o número de inteiros positivos coprimos com "n". Quando n é um número inteiro maior que 2, existem números pares e ímpares entre 1 e n - 1.
No entanto, os números pares são automaticamente excluídos dos valores coprimos com n, uma vez que qualquer número par maior que 1 será divisível por 2, o que significa que não é coprimo com n, já que n é maior que 2.

Isso implica que apenas os números ímpares entre 1 e n - 1 podem ser coprimos com n. E, uma vez que há mais números ímpares do que números pares em qualquer intervalo de números inteiros, a função totiente de Euler φ(n) para n > 2 sempre contará um número par de valores.

Podemos concluir que a afirmação é verdadeira para todos os n > 2, devido à exclusão dos números pares do conjunto de inteiros coprimos com n.

7. **Se n é composto e passa no teste de Miller-Rabin para a base a, então n é chamado de pseudo-primo forte à base a. Mostre que 2047 é um pseudoprimo à base 2.**


O teste de Miller-Rabin funciona da seguinte maneira: dada uma base "a" e um número ímpar composto "n", você escreve "n-1" na forma 2^r * d, onde "d" é ímpar. Então, você calcula as potências de "a" até chegar a "a^(d)" e faz verificações intermediárias para ver se alguma delas é congruente a 1 (mod n) ou a "n-1" (mod n). Se nenhuma dessas verificações for satisfeita, o número é considerado um pseudoprimo forte à base "a".

No caso de 2047:

$n = 2047$
$n - 1 = 2046 = 2 * 1023 = 2 * 3 * 341 = 2 * 3 * 11 * 31$

Agora, aplicamos o teste de Miller-Rabin com base 2:

Primeiro, calculamos $a^{d} \mod(n)$":
$a = 2$
$d = 1023$
$a^{d} \mod(n) = 2^{1023} \mod (2047)$
Vamos calcular "a^(d) mod n" usando o método da exponenciação rápida:

$a^1 = 2$
$a^2 = (a^1)^2 = 4$
$a^4 = (a^2)^2 = 16$
$a^8 = (a^4)^2 = 256$
$a^{16} = (a^8)^2 = 65536 ≡ 1632 \mod (2047)$
$a^{32} ≡ 1632^2 ≡ 228 \mod (2047)$
$a^{64} ≡ 228^2 ≡ 1441 \mod (2047)$
$a^{128} ≡ 1441^2 ≡ 1164 \mod (2047)$
$a^{256} ≡ 1164^2 ≡ 1719 \mod (2047)$
$a^{512} ≡ 1719^2 ≡ 505 \mod (2047)$
$a^{1023} ≡ 505^2 ≡ 1 \mod (2047)$

Agora, verificamos se $a^{d}$ é congruente a 1 (mod n) ou a $n-1 \mod (n)$:
Como $a^{d}$ é congruente a 1 (mod n), não é necessário verificar a outra condição.
Como $a^{d}$ é congruente a 1 (mod n), podemos concluir que 2047 passa no teste de Miller-Rabin para a base 2. Portanto, 2047 é um pseudoprimo forte à base 2.

8. O exemplo usado por Sun-Tsu para ilustrar o CRT foi
x = 2 (mod 3);
x = 3 (mod 5);
x = 2 (mod 7);
Solucione para x.