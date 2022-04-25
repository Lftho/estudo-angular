# Estudando angular

1. O que é observables ?

R: Emite notificações sempre que ocorre uma mudança em um de seus itens e a partir disto podemos executar uma ação, pois cada evento emitido é uma notificação para nosso Observable e então tratamos os dados.

Seu uso consiste em basicamente se inscrever (subscribe) que é uma Observable, informando o que deverá ser feito com o dado que irá receber. Essa inscrição poderá escutar 3 interações:
• sucesso
• erro
• completo(encerrado)

Podemos informar no próprio (subscribe), via parâmetro, as funções que devem ser executadas quando alguma dessas interações ocorrem, sendo somente função de sucesso obrigatória.

É importante ter em mente que ao emitr um erro, <strong>o Obsersable sempre encerrará sua execução</strong>, podendo passar algum dado. Ao completar, ele apenas encerra a execução, sem passar nenhum dado para os inscritos, apenas os informa que ele completou seu ciclo.

Podemos nos inscrever ao mesmo Observable <strong>mais de uma vez e em vários pontos da aplicação, tornando-os uma excelente alternativa para comunicação entre componentes</strong>

Resumo:
Resumidamente, com um Observable podemos:
• Receber dados várias vezes e em vários momentos
• Nos inscrever para receber dados de um mesmo Observable em vários pontos da aplicação
• Executar alguma operação quando o dado for recebido com sucesso
• Executar alguma operação quando emitir erro
• Executar alguma operação quando completar

Em breve explicação com exemplos.

2. Explicação de uso de lazy-loading ?

R: Uma vantagem de dividir a aplicação em módulos é a possibilidade de fazer o carregamento de determinados móduglos somente quando houver necessidade.
Quando se usa módulos 'Lazy Loading', o carregamento só é feito quando o usuário navega para a rota do respectivo módulo.

3. Qual é a diferença entre Angular e React?

R: React é uma ferramenta popular para começar no universo de frameworks, mas não é um framework. Isso significa que, diferente de Angular, não possui ferramentas próprias que juntas oferecem uma solução completa para o desenvolvimento front-end. Pelo contrário, o React é apenas uma base, uma coleção de funções que cria elementos reutilizáveis. A biblioteca auxiliar React DOM permitindo a inserção desses elementos em páginas web.

React é mais ligado à programação funcional. Dessa forma, as boas práticas de React são bem diferentes de boas práticas de Angular. Um dos principais pontos é que React não possui uma divisão clara de partes de um componente. Possui uma estrutura mais simples: um componente pode ser tanto uma classe como uma função. Se Angular é semelhante ao MVC, React foca apenas no "V" (view).

<hr />

Para quem nunca viu MVC, é importante entender que ele é um padrão de projeto baseado em modelos (os formatos dos dados), views (a representação dos dados que no front-end pode ser relacionada ao HTML) e controladores (entidades que funcionam como "gerentes", controlando os comportamentos baseado no que é solicitado).

No Angular trabalhamos com componentes que são, essencialmente, uma mistura de TypeScript e HTML que resulta em um código independente, isolado e reutilizável. Pense em componentes como elementos HTML com super-poderes. Um botão personalizado, uma tabela, um cabeçalho, e várias estruturas comuns podem ser componentes.

A síntese do MVC com componentes resulta na seguinte estrutura:

Um template, que é a linguagem de marcação, geralmente HTML. Representa a parte visual de um componente e pode ser entendida como a View.
A classe principal do componente, que é de fato o componente, todas as suas propriedades e seus métodos. No Angular, essa estrutura é criada com TypeScript.

Geralmente, trabalhamos com funções que retornam um código especial, uma linguagem de marcação: o JSX, uma extensão do JavaScript que adiciona a sintaxe do HTML, permitindo que páginas dinâmicas sejam criadas facilmente.

Ex: component de botão

- React:
  Um componente React pode ser pequeno graças ao JSX. Teremos uma função chamada Botao e a maior parte do seu dinamismo é resultante do parâmetro props (nome que vem de propriedades)

  Todo componente React pode receber propriedades que se assemelham a atributos do HTML. Além disso, children é um atributo especial que contém o conteúdo que foi passado dentro do componente (nesse caso, será o texto do botão).

  No JSX, JavaScript pode ser passado dentro de chaves ({}) e será interpretado.

  ```
    <div>
      export default function Botao(props) {
        return (
        <button title={props.titulo} onClick={props.aoClicar}>
          {props.children}
        </button>
      );
    }
    </div>
  ```

  ```
  Pontos positivos:

  - Flexibilidade para criar aplicações pequenas ou grandes;

  - Liberdade de trabalhar como preferir, inclusive podendo usar JavaScript ou TypeScript;

  - Comunidade muito ativa e preocupação com iniciantes. Criada e mantida pelo Facebook, usada por plataformas como Twitter e Netflix.
  ```

- Angular

  Um componente de botão pode conter:

  ```
    <div>
      <button [title]="titulo" (click)="aoClicar()">
        <ng-content></ng-content>
      </button>
    </div>
  ```

  No template podemos misturar HTML com algumas propriedades do próprio Angular: diretivas, atributos que implementam comportamentos, e ligação de dados, maneiras de passar dados dinâmicos como valores de atributos e conteúdo.

  A propriedade title do botão, por exemplo, pode receber um valor dinâmico (variável), para isso usamos os colchetes ([title]).

  Eventos podem receber métodos e são marcados com parênteses ((click)). Já <ng-content> é um elemento especial do Angular que não possui nenhuma representação visual, mas serve para criar trechos HTML dinâmicos. Nesse caso, será substituído pelo que for passado dentro do componente (processo chamado de Projeção de Conteúdo).

  ```
  Pontos positivos:

  - Várias implementações prontas que facilitam o processo de aprendizado e desenvolvimento;

  - Usado por grandes empresas. Criado e mantido pela Google que garante bom suporte e comunidade ativa.
  ```

3. Como utilizar o NgRx ?

R: ?
