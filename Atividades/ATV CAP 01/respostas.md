# Atividade Cap. 01 - Introdução
_______________________________
1. **O que é a arquitetura de segurança OSI?**

O modelo **OSI(Open System Interconection)** Tem como principal objetivo ser um modelo padrão para comunicação entre diversos tipo de sistemas. Trata-se de uma arquitetura model que divide em 7 as camadas de redes de computadores. Através desse modelo é possivel realizar comunicação entre máquinas distintas e definir diretivas genéricas para a comunição.

2. **Qual é a diferença entre ameaças à segurança passivas e ativas?**

Para cada tipo de ataque pode ocorrer a interceptação, modificação ou negação de um serviço. No **modo de ataque passivo** o agente invasor utiliza os dados obtidos para seu propósito próprio não afetando dados originais da fonte legítima. No **modo de ataque ativo** o agente utiliza-se de artifícios para interceptar, alterar e reintroduzir os dados no seu percurso original de forma que a fonte legítima e e entidade terceira não percebam.

3. **Liste e defina resumidamente as categorias de ataques passivos e ativos à segurança.**

*Ativos*

- **Máscara**: ocorre quando uma entidade finge ser uma entidade diferente.
- **Modificação de mensagens**: alguma parte de uma mensagem é alterada ou que a mensagem é atrasada ou reordenada para produzir um efeito não autorizado.
- **Repúdio**: O remetente ou destinatário pode negar posteriormente que enviou ou recebeu uma mensagem. Por exemplo, o cliente pede ao seu Banco “Para transferir uma quantia para alguém” e mais tarde o remetente (cliente) nega que tenha feito tal pedido.
- **Repetição**: Envolve a captura passiva de uma mensagem e sua posterior transmissão para produzir um efeito autorizado.
- **Negação de serviço**: impede o uso normal dos recursos de comunicação.

*Passivos*

- **A divulgação do conteúdo**: conversa telefônica, uma mensagem de correio eletrônico ou um arquivo transferido pode conter informações sensíveis ou confidenciais.
- **Análise de tráfego**: O oponente pode determinar a localização e a identidade do host em comunicação e pode observar a frequência e a duração das mensagens trocadas. Essas informações podem ser úteis para adivinhar a natureza da comunicação que estava ocorrendo.

4. **Liste e defina resumidamente as categorias dos serviços de segurança.**

- **Autenticação**: Refere-se à garantia de que uma comunicação é autêntica. No caso de uma única mensagem, como uma advertência ou um sinal de alarme, a função do serviço de autenticação é garantir ao destinatário que a mensagem tem a origem de que ela afirma ter vindo.
- **Controle de Acesso**: Capacidade de limitar e dominar o acesso aos sistemas
e aplicações por meio de links de comunicação.
- **Confidencialidade de dados**: proteção dos dados transmitidos contra ataques passivos.
- **Integridade de dados**: Pode se aplicar a um fluxo de mensagens, a uma única mensagem ou a campos selecionados dentro de uma mensagem.
- **Irretratabilidade**: impede que o emissor ou o receptor neguem uma mensagem transmitida.
- **Service de disponibilidade**: propriedade de um sistema ou de um recurso do sistema de ser acessível e utilizável sob demanda por uma entidade autorizada, de acordo com especificações de desempenho.

5. **Liste e defina resumidamente as categorias dos mecanismos de segurança.**

Codificação
Assinatura digital
Controle de acesso
Integridade de dados
Troca de autenticação
Preenchimento de tráfego
Controle de roteamento
Notarização

6. Considere um caixa eletrônico, ATM no qual os usuários fornecem um cartão e um número de identificação pessoal (senha). Dê exemplos de requisitos de confidencialidade, integridade e disponibilidade associados com esse sistema e, em cada caso, indique o grau de importância desses requisitos.

- **Confidencialidade**:
   - **Proteção dos dados do usuário**: É fundamental garantir que as informações sensíveis dos usuários, como dados pessoais e financeiros, sejam mantidas em sigilo absoluto. O acesso não autorizado a essas informações deve ser prevenido.
   - **Importância:** Alta. A confidencialidade é essencial para evitar o roubo de identidade, fraudes financeiras e outros tipos de abusos que podem ter consequências graves para os usuários.

- **Integridade**:
   - **Integridade dos dados de transação**: Todas as transações realizadas no caixa eletrônico devem ser registradas e armazenadas com precisão. Os dados não devem ser modificados ou corrompidos durante a transmissão, processamento ou armazenamento.
   - **Importância:** Alta. A integridade garante que as transações sejam executadas corretamente e que os registros sejam confiáveis. Qualquer alteração indevida nos dados pode levar a erros nas transações ou perda de confiança no sistema.

- **Disponibilidade**:
   - **Disponibilidade contínua do sistema**: O ATM deve estar sempre disponível para uso pelos usuários, exceto durante manutenção programada ou em caso de falhas inesperadas. O tempo de inatividade do sistema deve ser minimizado.
   - **Importância:** Alta. A disponibilidade é crucial, pois os usuários dependem do acesso aos serviços do ATM para realizar transações financeiras. Qualquer interrupção prolongada do sistema pode causar inconvenientes significativos para os usuários e prejudicar a reputação do banco.

7. **Para responder as letras abaixo, por favor, consulte o livro-texto da disciplina:**
**(a)** Desenhe uma matriz similar ao Quadro 1.4 que mostre o relacionamento entre serviços de segurança e ataques.


| SERVIÇO                              | Máscara   | Modificação de mensagens | Repúdio | Negação de servicos | Repetição | Análise de tráfego |
|--------------------------------------|:---------:|:------------------------:|:-------:|:-------------------:|:---------:|:------------------:|
| Autenticação de entidade pareada     | X         |                          |         |                     |   X       |                    |
| Autenticação da origem de dados      |           |         X                |         |                     |           |                    |
| Controle de acesso                   | X         |                          |         |                     |           |                    |
| Confidencialidade                    | X         |         X                |         |                     |           |                    |
| Confidencialidade do fluxo de tráfego|           |         X                |         |                     |           |  X                 |
| Integridade de dados                 |           |         X                |         |                     |           |                    |
| Responsabilização                    | X         |                          |   X     |                     |           |                    |
| Disponibilidade                      |           |                          |         |         X           |           |                    |


**(b)** Desenhe uma matriz similar ao Quadro 1.4 que mostre o relacionamento entre mecanismos de segurança e ataques.

| MECANISMO                | Máscara   | Modificação de mensagens | Repúdio | Negação de servicos | Repetição | Análise de tráfego |
|--------------------------|:---------:|:------------------------:|:-------:|:-------------------:|:---------:|:------------------:|
|Codificação               |           |                          |         |                     |           |     X              |
|Assinatura digital        |  X        |                          |         |                     |   X       |                    |
|Controle de acesso        |  X        |                          |         |                     |   X       |                    |
|Integridade de dados      |           |      X                   |         |                     |           |                    |
|Troca de autenticação     |  X        |                          |         |                     |   X       |                    |
|Preenchimento de tráfego  |           |                          |         |                     |           |     X              |
|Controle de roteamento    |           |      X                   |         |                     |           |                    |
|Notarização               |  X        |      X                   |         |                     |           |                    |

## FONTES
__________________

- NASCIMENTO, ANDERSON. 2014. [O que é Modelo OSI?](https://canaltech.com.br/produtos/o-que-e-modelo-osi/). Acessado em: 07-07-2023.
- JOHNSON,H.; MALLADI, S. [Segurança em Sistemas](http://www.dsc.ufcg.edu.br/~peter/cursos/sds/Material/p1b.pdf). Acessado em: 07-07-2023.
- OLIVEIRA, ARLEI. 2023. [Tipos de Ataques (Ativo e Passivo) em Segurança da Informação](https://www.linkedin.com/pulse/tipos-de-ataques-ativo-e-passivo-em-seguran%C3%A7a-da-arlei-oliveira/?originalSubdomain=pt). Acessado em: 07-07-2023.
- ACERVO LIMA. [ATAQUES ATIVOS E PASSIVOS EM SEGURANÇA DA INFORMAÇÃO](https://acervolima.com/ataques-ativos-e-passivos-em-seguranca-da-informacao/). Acessado em: 07-07-2023.