# Atividade Cap. 07 - Geração de números pseudo-aleatorios

1. **Qual é a diferença entre aleatoriedades estatísticas e imprevisibilidade?**

A *aleatoriedade* estatística refere-se à variabilidade inerente que ocorre em dados e fenômenos que são sujeitos a processos aleatórios. A *imprevisibilidade* está relacionada à incapacidade de prever ou antecipar um evento ou resultado com certeza.

2. **Liste considerações de projeto importantes para uma cifra de fluxo.**

**Propriedades Criptográficas**

*Confidencialidade*: A cifra deve produzir sequências de números aparentemente aleatórios que não podem ser facilmente previsíveis, garantindo a confidencialidade dos dados.
*Integridade*: A cifra deve impedir a manipulação ou adulteração dos dados durante a transmissão.
*Autenticidade*: A cifra deve permitir que as partes envolvidas verifiquem a autenticidade dos dados gerados.

**Algoritmo Forte**

O algoritmo subjacente deve ser robusto e resistente a ataques criptográficos conhecidos, como ataques de análise diferencial, ataques de canal lateral, entre outros.
**Chave Secreta**

O gerador de números pseudoaleatórios deve depender de uma chave secreta forte para garantir que os resultados gerados sejam previsíveis apenas para aqueles que possuem a chave.

**Não-Previsibilidade**

Os números gerados não devem exibir padrões previsíveis, mesmo quando um adversário possui conhecimento parcial do estado interno do gerador.

**Distribuição Uniforme**

Os números gerados devem ser distribuídos de forma aproximadamente uniforme ao longo do espaço de saída.

**Período Longo**

O período da sequência gerada (o número de valores antes que a sequência se repita) deve ser suficientemente longo para evitar repetições e padrões.

**Inicialização Segura**

O estado inicial do gerador deve ser escolhido de forma segura, preferencialmente com base em uma chave secreta ou semente aleatória forte.

**Resistência a Ataques de Força Bruta**

O gerador deve ser projetado para resistir a ataques que tentam adivinhar a chave secreta por meio de força bruta.

**Avaliação de Desempenho**

A eficiência do algoritmo deve ser avaliada, levando em conta a velocidade de geração de números aleatórios e o uso de recursos computacionais.
Avaliação de Vulnerabilidades:

Realizar análises de segurança para identificar possíveis vulnerabilidades e fraquezas no algoritmo.

**Testes Estatísticos**

Realizar testes estatísticos para verificar se a sequência gerada passa por diferentes testes de aleatoriedade e distribuição.

**Atualizações e Manutenção**

Planejar um processo para atualizar o algoritmo, se necessário, em resposta a novos avanços em criptografia ou novas ameaças identificadas.

**Padrões e Normas**

Seguir padrões e diretrizes criptográficas reconhecidas, como aqueles estabelecidos por organizações como o NIST (Instituto Nacional de Padrões e Tecnologia).

**Revisões Independentes**

Submeter o algoritmo a revisões independentes e análises de especialistas em segurança para identificar possíveis problemas.


3. **Por que não é desejável reutilizar uma chave de cifra de fluxo?**

Não é desejável reutilizar uma chave de cifra de fluxo por várias razões, principalmente devido às vulnerabilidades de segurança que podem surgir quando a mesma chave é usada repetidamente. Quando uma chave é reutilizada, a sequência de bits gerada pela cifra de fluxo também será repetida. Isso pode resultar em padrões previsíveis nos dados criptografados. Adversários podem explorar esses padrões para realizar ataques de criptoanálise e recuperar informações sensíveis.

4. **Que operações primitivas são usadas no RC4?**

O RC4 (Rivest Cipher 4) é um algoritmo de cifra de fluxo que foi amplamente utilizado no passado, mas devido a vulnerabilidades e avanços na criptografia, não é mais considerado seguro para uso em aplicações modernas. No entanto, o RC4 é um exemplo interessante de um algoritmo de cifra de fluxo que utiliza operações primitivas relativamente simples para gerar uma sequência pseudoaleatória de bytes.

As operações primitivas usadas no RC4 incluem principalmente operações de permutação (troca de posições) e operações de substituição (substituição de valores).

**Inicialização e Geração de Estado**
O RC4 começa com uma inicialização, onde uma chave secreta é usada para criar um estado interno (geralmente uma matriz de 256 bytes). A permutação desse estado é realizada usando uma combinação de trocas de valores com base nos valores da chave.

**Swap de Valores**
O algoritmo faz várias iterações (geralmente 256 iterações) de trocas de valores no estado interno. Isso envolve a troca de elementos de matriz em posições específicas. Essa troca de valores é o cerne do algoritmo RC4 e é responsável por misturar os valores no estado.

**Geração da Sequência de Saída**
Após o processo de inicialização e mistura, o RC4 gera uma sequência pseudoaleatória de bytes (geralmente chamados de keystream) a partir do estado interno permutado. Essa sequência é usada para criptografar ou descriptografar os dados de entrada.

5. **Se apanharmos um algoritmo de congruência linear com um componente aditivo de 0:
$$ X_{n+1} = (aX_n) \mod(m) $$
Então, podemos mostrar que, se *m* é primo, e se determinado valor de *a* produz o período máximo de *m* − 1, então *$ a^k $* também produzirá o período máximo, desde que *k* seja menor que *m* e que *m* − 1 não seja divisível por *k*. Demonstre isso usando $ X_0 = 1 $ e m = 31, e produzindo as sequências para ak = 3, 3² , 3³ e 3⁴.**

Valores de interesse:

m = 31 (primo)
Período máximo = m - 1 = 30
a = 3
Agora, vamos calcular as sequências para $a^k$:

$a^1 = 3^1 = 3$
$a^2 = 3^2 = 9$
$a^3 = 3^3 = 27$
$a^4 = 3^4 = 81 \equiv 19 \pmod{31}$ (usamos a propriedade de congruência $81 \mod 31 = 19$)
Agora, calcularemos as sequências para cada valor de $a^k$:

Para $k = 1$:

$X_0 = 1$
$X_1 = (3 \cdot 1) \mod 31 = 3$
Para $k = 2$:

$X_0 = 1$
$X_1 = (3 \cdot 1) \mod 31 = 3$
$X_2 = (3 \cdot 3) \mod 31 = 9$
Para $k = 3$:

$X_0 = 1$
$X_1 = (3 \cdot 1) \mod 31 = 3$
$X_2 = (3 \cdot 3) \mod 31 = 9$
$X_3 = (3 \cdot 9) \mod 31 = 27$
Para $k = 4$:

$X_0 = 1$
$X_1 = (3 \cdot 1) \mod 31 = 3$
$X_2 = (3 \cdot 3) \mod 31 = 9$
$X_3 = (3 \cdot 9) \mod 31 = 27$
$X_4 = (3 \cdot 27) \mod 31 = 19$
Observamos que, para todos os valores de $k$ escolhidos (1, 2, 3 e 4), as sequências geradas têm o mesmo período máximo de 30 (m - 1), indicando que a afirmação é verdadeira.

Portanto, no caso específico de **$X_0 = 1$**, ***m = 31***, e ***a = 3***, podemos concluir que se m é primo e um determinado valor de a produz o período máximo de m - 1, então $a^k$ também produzirá o período máximo, desde que ***k*** seja menor que m e que ***m - 1*** não seja divisível por ***k***.

6.
**(a) Qual é o período máximo que pode ser obtido do seguinte
gerador $ X_{n+1} = (aX_n) \mod(2^4) $ ?**

O período máximo de um gerador de números pseudoaleatórios é determinado pelo tamanho do espaço de estados possível, que é a gama de valores distintos que o gerador pode gerar antes de repetir uma sequência anterior. 
Neste caso, o módulo é $2^4 = 16$, o que significa que o gerador pode gerar valores no intervalo de 0 a 15. 

Se ***a*** for relativamente primo a 16, ou seja, não tem fatores comuns com 16, então o período máximo será 16. Isso ocorre porque cada valor de $X_n$ será único para cada valor anterior, e não haverá repetições até que todos os valores possíveis sejam esgotados.
Se ***a*** tiver fatores em comum com 16, o período máximo será menor que 16. Isso ocorre porque o gerador não será capaz de gerar todos os possíveis valores dentro do espaço de estados antes de começar a repetir.

**(b) Qual deverá ser o valor de a?**

Para que o gerador X_{n+1} = (aX_n) \mod(2^4) alcance um período máximo de 16, o valor de "a" precisa ser relativamente primo a 16. Isso significa que "a" não deve ter fatores comuns com 16, exceto o fator 1.

Os fatores primos de 16 são 2 e 2 novamente (16 = 2^4). Portanto, qualquer valor de "a" que não seja divisível por 2 será relativamente primo a 16 e proporcionará um período máximo de 16.

Aqui estão alguns exemplos de valores possíveis para "a" que atenderiam a esse critério:

a = 1
a = 3
a = 5
a = 7
a = 9
a = 11
a = 13
a = 15

Esses valores de "a" não têm fatores comuns com 16, além do fator 1, e, portanto, permitiriam um período máximo de 16 para o gerador.


**(c) Que restrições são exigidas na semente?**

A semente, também conhecida como valor inicial ou chave de inicialização, é um componente importante em algoritmos de geração de números pseudoaleatórios (PRNGs). A qualidade da semente influencia diretamente a qualidade e a segurança da sequência pseudoaleatória gerada pelo algoritmo.

**Unicidade**: Cada semente deve ser única para evitar que sequências idênticas sejam geradas. O uso da mesma semente levará sempre à mesma sequência de números pseudoaleatórios.

**Aleatoriedade**: Idealmente, a semente deve ser o mais aleatória possível. Se a semente não for verdadeiramente aleatória, pode introduzir padrões na sequência gerada. Sementes baseadas em eventos não previsíveis, como o tempo exato de inicialização, podem melhorar a aleatoriedade.

**Não Previsibilidade**: A semente não deve ser previsível para adversários. Se a semente for facilmente adivinhada ou determinada, um atacante pode ser capaz de prever a sequência pseudoaleatória e comprometer a segurança da aplicação.

**Tamanho Suficiente**: A semente deve ter um tamanho suficiente para garantir a segurança e a variedade da sequência gerada. Sementes muito curtas podem resultar em ciclos pequenos ou na repetição rápida de valores.

**Proteção e Confidencialidade**: A semente deve ser tratada como informação sensível e protegida contra acesso não autorizado. Se um adversário obtiver acesso à semente, pode ser capaz de prever a sequência de números pseudoaleatórios e explorar vulnerabilidades.

**Atualização Regular**: Em sistemas que requerem alta segurança, como criptografia, é aconselhável atualizar a semente periodicamente para garantir que uma sequência longa e previsível não seja gerada.

**Origem Criptográfica (Opcional)**: Para aplicações criptográficas, é recomendável usar uma semente que tenha origem criptográfica, o que significa que foi gerada por um processo confiável e altamente entropia (entropia é uma medida de aleatoriedade). 

7. **Que valor de chave RC4 deixará S inalterado durante a inicialização? Ou seja, após a permutação inicial de S, as entradas de S serão quais aos valores de 0 a 255 na ordem crescente.**

Para que o estado interno *S* no algoritmo RC4 permaneça inalterado após a permutação inicial, a chave de inicialização deve ser uma sequência de valores de 0 a 255, na ordem crescente. O algoritmo RC4 envolve a permutação do estado interno *S* com base nos valores da chave de inicialização. Quando a chave de inicialização é uma sequência ordenada de 0 a 255, a permutação resultará em *S* permanecendo na mesma ordem.

Em outras palavras, se a chave de inicialização for "0 1 2 3 ... 254 255", após a permutação inicial, os valores em *S* serão "0 1 2 3 ... 254 255", respectivamente. Isso ocorre porque a permutação usa os valores da chave para definir as posições iniciais do estado interno.

Essa situação é uma característica específica que ocorre quando a chave é uma sequência ordenada e é uma particularidade do algoritmo RC4. No entanto, é importante notar que o RC4 não é mais considerado seguro para uso em aplicações criptográficas, devido a várias vulnerabilidades identificadas ao longo dos anos. Portanto, não é recomendável utilizar o RC4 para fins de segurança.

8. **O algoritmo Blum Blum Shub é baseado na teoria dos resíduos quadráticos e utiliza três números inteiros para realizar os cálculos: p, q e s.**

**(a) Escolha dois números primos grandes *p* e *q*, onde *p* e *q* sejam congruentes a $3 \mod(4)$ e não tenham fatores primos comuns. Por exemplo, você pode escolher p = 499 e q = 503.**

p = 9187, q = 9199

**(b) Calcule n = p ∗ q. Neste caso, n seria igual a 499 ∗ 503 = 250997.**

n = 9187 * 9199 = 84511213

**(c) Escolha um número inteiro s entre 1 e n − 1 que seja co-primo com n. Por exemplo, você pode escolher s = 17.**

co-primo = 17572

**(d) Calcule o valor inicial $x_0 = (s^2) \mod(n)$. Neste caso, $x_0$ seria igual a ($17^2$) mod 250997 = 289.**

$x_0 = 17572² = 308775184$
$308775184 \mod(84511213) = 55241545$

**(e) Agora, vamos gerar uma sequência de números aleatórios usando o algoritmo Blum Blum Shub. Para gerar cada número da sequência, use a seguinte fórmula: $x_i = (x^2_{i− 1} ) \mod(n)$.**
$n = 84511213$
$x_0 = 17572$

**(f) Execute a fórmula várias vezes para gerar uma sequência de números aleatórios. Por exemplo, você pode executar a fórmula 10 vezes para obter 10 números aleatórios.
Aqui está a sequência de números aleatórios gerados usando o algoritmo Blum Blum Shub com os valores do exemplo: 289, 253306, 14107, 23546, 67740, 144593, 79829, 46219, 132936, 9863
Qual foi a sua sequência?**

$x_1 = x_0² \mod(n) = 17572² \mod(n) = 308775184 \mod(n) = 55241545$
$x_2 = x_1² \mod(n) = 55241545² \mod(n) = 3051628293987025 \mod(n) = 58065649$
$x_3 = x_2² \mod(n) = 58065649² \mod(n) = 3371619593791201 \mod(n) = 44724524$