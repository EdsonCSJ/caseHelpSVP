# CaseHelpSVP
Projeto da trilha de engenharia de software da Unisinos.

O projeto se trata de uma aplicação voltada ao gerenciamento de um lar de idosos.

## Necessidades

- Diretor Financeiro: Gerenciar as contas do lar e prover visibilidade ao lar
- Usuário Externo: Realizar doações
## Problemas Solucionados

### Diretor Financeiro:

O sistema permite gerenciar as contas do lar, permitindo criar contas a receber (valores que entram) e a pagar (valores que saem/são pagos a outrora) buscando ter melhor controle sobre o que foi pago ou não. Assim como gerar relatórios no Excel das contas dos últimos 30 dias;
Gerenciar os eventos do lar, permitindo criar eventos e notificar os usuários cadastrados no sistema sobre a data e local do mesmo.

### Usuário Externo:

O sistema permite realizar doações online para melhor conveniência ao realizar uma doação.


## Tecnologias Utilizadas
O projeto utiliza Docker para build e está dividido em 3 containers:

Frontend: Criado com ReactJS através do uso do framework NextJS. Se comunica com a API;
Backend (API): Criada com ExpressJS, responde ao frontend e se comunica com o banco de dados. Utiliza bibliotecas como Sequelize, CryptoJS, Jsonwebtoken, entre outras;
Banco de Dados: Criado com o MySQL.

## INSTALAÇÃO DA APLICAÇÃO CASEHELPSVP

1. Instalar o Docker;
2. Clonar este repositório;
2. Extrair os arquivos de “CaseHelpSVP.zip” para um diretório;
3. Entrar no diretório criado através do terminal e executar o comando para instalar e rodar a aplicação:

`docker-compose up --build -d`

Após o término, é necessário criar um usuário administrador (no caso, é um Diretor Financeiro). Os dados (exceto a senha) podem ser substituídos no comando. Portanto, ainda no terminal, executar:

`docker exec -i mysqldb mysql -uroot -proot casehelpsvp -e "insert into users (admin, cellphone, cpf, createdAt, disabled, email, name, password, updatedAt) values (1, '12128119182', '12345678911', '2021-11-24 15:30:46', 0, 'email@email.com', 'Diretor Financeiro', '$2b$10$5IyHE9mFrYK5LkAA/1q9QeTt4rnlXu4k/hMZMlf5Amh1USN2j/TRS', '2021-11-24 15:30:46');"`

O login do usuário é o e-mail (email@email.com) e a senha é 123456.

Após isso, basta acessar o site através da url: http://localhost:3000  (o primeiro carregamento pode demorar um pouco mais que o normal).
Para enviar e-mails, logar como diretor financeiro e acessar as configurações preenchendo o SMTP com um e-mail válido.
