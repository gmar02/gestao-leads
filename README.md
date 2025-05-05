# Digrama UML de classes

## Geral

* feito com intuitos acadêmicos
* representa modelagem inicial para sistema de gestão de leads

## Dependências

* <a href="https://marketplace.visualstudio.com/items?itemName=jebbs.plantuml">Extensão para PlantUML (VSCode)</a>
* <a href="https://graphviz.org/download/">Graphviz para visualização</a>

## Descrição Lógica

* 5 entidades principais: Usuário, Perfil, Evento, Formulário e Candidato.

  * `Usuário` representa o usuário do sistema;
  * `Perfil` fornecerá informações para controle de acesso;
  * `Evento` representa o evento onde ocorrerá a captação de leads;
  * `Candidato` representa a pessoa que deseja ingressar na instituição (uma lead);
  * `Formulário` contém informações necessárias para gerar o formulário de cadastro de `Candidato` no `Evento`

* funcionamento básico

  * usuário com perfil 'admin' pode cadastrar usuários de perfil 'consultor';
  * usuário com perfil 'consultor' pode cadastrar `eventos` e `gerar formulario` para cada evento específico;
  * cada `Evento` possui um único QR-Code que redireciona o `Candidato` a um `Formulario` cujas instâncias serão responsáveis por cadastrá-lo;

* notas importantes

  * o link (ou path variable) para código QR pode ser persistido em HASH para evitar vazamentos
  * o `Formulario` possui validade. Após vencimento, não será mais possível utiliza-lo
  * os campos `Candidato.email` e `Candidato.curso_de_interesse` são opcionais