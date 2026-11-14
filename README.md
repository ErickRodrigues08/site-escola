# EduGestão — Sistema Escolar

EduGestão é uma aplicação web em PHP para apoiar a comunicação e a organização escolar. Alunos, professores e administradores acessam um painel com avisos e atividades por turma. O sistema inclui cadastro, login e controle de acesso por tipo de usuário.

## Funcionalidades

- Cadastro e autenticação de usuários por e-mail e senha.
- Perfis de aluno, professor e administrador.
- Dashboard com resumo de avisos, atividades e usuários.
- Publicação, edição e exclusão de avisos por administradores.
- Cadastro, edição, listagem e exclusão de atividades por professores e administradores.
- Filtragem de atividades por turma e visualização de prazos.
- Interface responsiva com estilos em CSS.

## Tecnologias

- PHP 8.0 ou superior
- MariaDB 10.4+ ou MySQL compatível
- PDO para acesso ao banco de dados
- HTML e CSS

## Requisitos

- PHP com as extensões PDO e PDO MySQL habilitadas
- MariaDB ou MySQL
- Servidor web com suporte a PHP, como Apache (XAMPP) ou o servidor embutido do PHP

## Instalação local

1. Clone ou baixe este repositório e abra um terminal na pasta do projeto.
2. Crie o banco de dados:

   ```sql
   CREATE DATABASE gestao_escolar
     CHARACTER SET utf8mb4
     COLLATE utf8mb4_general_ci;
   ```

3. Importe `gestao_escolar.sql` para o banco `gestao_escolar`, por exemplo pelo phpMyAdmin ou pelo terminal:

   ```bash
   mysql -u root -p gestao_escolar < gestao_escolar.sql
   ```

4. Configure host, banco, usuário e senha da conexão em `includes/conexao.php` para o seu ambiente local.
5. Inicie o servidor na raiz do projeto:

   ```bash
   php -S localhost:8000
   ```

6. Acesse [http://localhost:8000](http://localhost:8000). Crie uma conta pela opção **Criar conta** e entre pelo login.

> A conexão atualmente usa as configurações definidas em `includes/conexao.php`. Não publique senhas ou credenciais reais no repositório.

## Estrutura do projeto

```text
.
├── atividades.php       # Gestão e consulta de atividades
├── avisos.php           # Gestão e consulta de avisos
├── cadastro.php         # Cadastro de usuários
├── dashboard.php        # Painel com resumo do sistema
├── index.php            # Página inicial
├── login.php            # Autenticação
├── logout.php           # Encerramento da sessão
├── gestao_escolar.sql   # Estrutura do banco de dados
├── css/
│   └── style.css        # Estilos da aplicação
└── includes/
    ├── conexao.php      # Conexão PDO com o banco
    └── sidebar.php      # Navegação lateral
```

## Tipos de usuário

- **Aluno:** consulta avisos e atividades.
- **Professor:** consulta e gerencia atividades.
- **Administrador:** gerencia avisos e tem acesso ao resumo de usuários.

## Observação de segurança

O formulário de cadastro permite selecionar o tipo de usuário, inclusive administrador. Essa configuração é adequada apenas para testes locais; antes de disponibilizar o sistema publicamente, restrinja a criação de contas administrativas e revise as permissões e a configuração do banco.

## Licença

Este projeto está sob a licença MIT. Consulte o arquivo `LICENSE`.
