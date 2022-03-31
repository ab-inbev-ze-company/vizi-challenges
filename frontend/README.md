# **Desafio Frontend Vizi**

Primeiramente, obrigado pelo seu interesse em trabalhar na Vizi, a geladeira de bebidas com preço de mercado, dentro do seu condomínio.

Abaixo você encontrará todos as informações necessárias para iniciar o seu teste.

## Avisos antes de começar

- Para iniciar o teste, crie um repositório público no GitHub.
- Ao finalizar o teste, nos envie o link do seu repositório.
- Fique à vontade para entrar em contato e tirar qualquer dúvida.
- Respire antes de começar e durante o teste, assim como você, também já passamos por essa etapa. Boa sorte! :)


## Pré-requisitos para o teste

- React ou React Native. Não é obrigatório, fique a vontade para utilizar o que mais lhe deixa confortável.
- Dê preferência por utilizar Typescript
- Utilizar a api mencionada abaixo.

## Como Rodar a api?
- Após criar a estrutura do seu projeto, instale o JSON Server **`npm i json-server`** como dependência
- Copie os arquivos **`db.json`** e **`api.js`** presentes neste repositório para a pasta do seu projeto
- Rode seu fake REST API com este comando **`node api.js`**
- Seu fake REST API deve estar disponível na porta 3000 `http://localhost:3000`

## Leia com atenção!

Nosso desafio consiste em trazer o dia a dia da Vizi para dentro do seu teste, então você terá o desafio de criar um sistema com 3 páginas;

**`Página Principal:`** Serão listados 15 produtos exibindo o nome, preço e a sua imagem. Nesta tela, deverá ter um botão "Destrancar Porta" (Pode utilizar ícone ou estilizar como achar mais adequado), ao clicar nesse botão, será chamado o serviço para criar uma nova transação. Após esse retorno, você utilizará os dados do retorno para chamar o serviço de pagamentos e assim, finalizar seu fluxo de compra.

**`Página Pagamentos:`** Nesta página, será necessário listar todos os pagamentos já feitos, mostrando a data, valor da compra e qual o status de pagamento.

**`Página Detalhe do Pagamento:`** Estando na página de **`Pagamentos`**, precisamos ter alguma forma de ver os detalhes desse pagamento. Ao acessar a página de detalhe, devo conseguir visualizar tanto as informações do pagamento, quanto da transação que gerou a ordem de pagamento. Exibindo a data de pagamento, data de abertura/fechamento da geladeira, produtos com seus detalhes e o valor total da compra.

Abaixo está detalhado os serviços e como funciona sua utilização:

- Rota **`/products`**, nela você fará um GET para listar os 15 produtos em sua página principal, tendo que exibir o nome, preço e a imagem.

- Rota **`/transactions`**, nela você fará um POST, não é necessário passar dados no body, propositalmente, o serviço demora 3 segundos para dar uma resposta, retornará os seguintes campos:
    - id: Id único gerado randomicamente;
    - openFridge: Data que o serviço foi chamado;
    - closeFridge: Data do campo openFridge adicionando 1 minuto;
    - products: Retorna randomicamente os mesmo produtos do serviço `/products`, porém, adicionando o campo **quantity** que também é um valor randômico;

- Rota **`/payments`**,  esta rota servirá tanto para criar um pagamento pelo POST (passando os campos `transactionId` e `amount` no body), quanto para listar todos os pagamentos pelo GET, retornará esses campos:
    - id: Id único gerado randomicamente;
    - paymentDate: Data em que os serviço foi chamado;
    - transactionId: Id da transação que gerou a ordem de pagamento;
    - amount: É a soma de todos os produtos da `/transaction` multiplicando por sua quantidade;
    - status: PAID ou REJECTED, o valor é retornado randomicamente;

- Rota **`/transactions/{id}`** e **`/payments/{id}`**, ao clicar em um pagamento para exibir os detalhes, já que nos dados do pagamento você tem o campo **transactionId**, é possível buscar os dados somente daquele registro dessa forma **`/transactions/{valor do campo transactionId}`**

Para melhorar o entendimento da api, dentro da pasta **`assets`** nesse repositório, tem alguns prints do fluxo.
<br/>
<br/>

**Orientações e dicas:**

- Esperamos que você consiga completar o mínimo do desafio. Mas fique a vontade para nos surpreender com o seu melhor! 😉

- Iremos avaliar cada feature, conceito, pattern, tudo o que você fizer de adicional. Tudo além do proposta contará pontos!

- Caso você esteja concorrendo a uma vaga de Sênior, testes unitários são necessários no teste. Se você estiver concorrendo a uma vaga de JR ou Pleno, não é obrigatorio, mas é um grande diferencial caso seja aplicado os testes.

- Faça commits regulares. Eles são melhores do que um commit gigantesco. Gostaríamos de ver commits organizados e padronizados, então capriche neles!

Qualquer problema por favor, entre em contato.

**BOA SORTE !** 🚀🚀🚀