# Conventional Commits  Pattern

## Structure

**!type(?scope): !subject** <br/> 
**?description**
<br/>
<br/>
Example:

>   docs(readme): update subtitle references

***

## Type

O type é responsável por nos dizer qual o tipo de alteração ou iteração está sendo feita, das
regras da convenção, temos os seguintes tipos:

*   **TEST** : Indica qualquer tipo de criação ou alteração de códigos de teste. Exemplo: Criação de testes unitários.
<br/>

*   **FEAT** : Indica o desenvolvimento de uma nova feature ao projeto. Exemplo: Acréscimo de um serviço, funcionalidade, endpoint, etc.
<br/>

*   **REFACTOR** : Usado quando houver uma refatoração de código que não tenha qualquer
tipo de impacto na lógica/regras de negócio do sistema. Exemplo: Mudanças de
código após um code review
<br/>

*   **STYLE** : Empregado quando há mudanças de formatação e estilo do código que não
alteram o sistema de nenhuma forma.Exemplo: Mudar o style-guide, mudar de convenção lint, arrumar indentações, remover espaços em brancos, remover comentários, etc..
<br/>

*   **FIX** : Utilizado quando há correção de erros que estão gerando bugs no sistema.
Exemplo: Aplicar tratativa para uma função que não está tendo o comportamento
esperado e retornando erro.
<br/>

*   **CHORE** : Indica mudanças no projeto que não afetem o sistema ou arquivos de testes. São mudanças de desenvolvimento.
Exemplo: Mudar regras do eslint, adicionar prettier, adicionar mais extensões de arquivos ao .gitignore
<br/>

*   **DOCS** : Usado quando há mudanças na documentação do projeto.
Exemplo: adicionar informações na documentação da API, mudar o README, etc.
<br/>

*   **BUILD** : Uilizada para indicar mudanças que afetam o processo de build do projeto ou dependências externas. Exemplo: Gulp, adicionar/remover dependências do npm, etc.
<br/>

*   **PERF** : Indica uma alteração que melhorou a performance do sistema.
Exemplo: alterar ForEach por while, melhorar a query ao banco, etc.
<br/>

*   **CI** : Utilizada para mudanças nos arquivos de configuração de CI.
Exemplo: Circle, Travis, BrowserStack, etc.
<br/>

*   **REVERT** : Indica a reverão de um commit anterior.
<br/>

***

## Scope

Mesmo não sendo obrigatório, ele pode ser utilizado para contextualizar o commit e trazer menos responsabilidade para a mesmo o description, uma vez que dispondo do tipo de commit e o contexto que foi aplicado, a mensagem deve ser o mais breve e concisa possível.

    Exemplo: refactor(web/mobile): change create user logs

***

## Subject

Usar o imperativo ao inves do preterito.

    fix: changed the log [ERROR]
    fix: change the log [OK]

### Command Git:

    git commit -m "Subject" -m "My description."

## Links

<https://medium.com/linkapi-solutions/conventional-commits-pattern-3778d1a1e657>