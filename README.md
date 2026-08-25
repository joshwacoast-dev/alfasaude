<div align="center">

# 🏥 Alfa Saúde — Sistema de Gestão Clínica

[![PHP](https://img.shields.io/badge/PHP-8.0%2B-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-5.7%2B-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![XAMPP](https://img.shields.io/badge/XAMPP-Supported-FB7A24?style=for-the-badge&logo=xampp&logoColor=white)](https://www.apachefriends.org/)
[![Web Hosting](https://img.shields.io/badge/Online%20Server-cPanel%20%7C%20VPS-008080?style=for-the-badge&logo=cpanel&logoColor=white)](#)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](#)

Sistema web completo para gestão integrada de clínicas, agendamentos, prontuários eletrônicos e controle de pacientes.

[Visitar Website](https://alfasistemas.dev.br) • [Reportar Bug](https://alfasistemas.dev.br) • [Solicitar Recurso](https://alfasistemas.dev.br)

</div>

---

## 📸 Capturas de Tela

| Dashboard Principal | Gestão de Agendamentos |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/1be75638-c7b6-4fbe-8019-df32b87f2ecb" width="100%" alt="Dashboard Alfa Saúde" /> | <img src="https://github.com/user-attachments/assets/b87f8796-567d-458e-acfd-bddaa01b2d27" width="100%" alt="Agendamentos" /> |

| Prontuário Eletrônico | Cadastro de Pacientes |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/6a1e6c83-2fef-4cb2-bb71-c4b9aa8656d3" width="100%" alt="Prontuário Eletrônico" /> | <img src="https://github.com/user-attachments/assets/930b97b7-ab75-45ea-a134-366effe68f3a" width="100%" alt="Cadastro de Pacientes" /> |

| Emissão de Documentos | Relatórios e Progresso |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/9a5a6b19-c9b3-4a9f-a9f2-e38ca27f36b2" width="100%" alt="Emissão de Documentos" /> | <img src="https://github.com/user-attachments/assets/1f0670a1-ec87-47c8-b867-81047259a6cd" width="100%" alt="Progresso do Paciente" /> |

| Configurações da Clínica | Modo Escuro (Dark Mode) |
| :---: | :---: |
| <img src="https://github.com/user-attachments/assets/e16ec72c-fb29-4c23-a79e-7f4fe1d4cabe" width="100%" alt="Configurações da Clínica" /> | <img src="https://github.com/user-attachments/assets/492675c4-74ca-42ca-92bc-a7f4f9fc9fef" width="100%" alt="Modo Escuro" /> |

---

## 📌 Índice
- [Recursos do Sistema](#-recursos-do-sistema)
- [Pré-requisitos](#-pré-requisitos)
- [Instalação e Configuração](#-instalação-e-configuração)
  - [🖥️ Opção 1: Instalação Online (Servidor Web / Hospedagem / VPS)](#️-opção-1-instalação-online-servidor-web--hospedagem--vps)
  - [💻 Opção 2: Instalação Local com XAMPP](#-opção-2-instalação-local-com-xampp)
- [Acesso Inicial](#-acesso-inicial)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Personalização](#-personalização)
- [Solução de Problemas](#-solução-de-problemas)
- [Suporte e Contato](#-suporte-e-contato)

---

## ⚡ Recursos do Sistema

* **Gestão de Pacientes:** Cadastro completo, histórico clínico e acompanhamento de progresso.
* **Prontuário Eletrônico:** Emissão de receituários, declarações e registros de consultas.
* **Agendamentos:** Controle de horários e status de consultas.
* **Personalização:** Suporte a tema escuro, alteração de paleta de cores e upload de logotipo.
* **Segurança:** Logs de acesso detalhados e controle de autenticação de usuários.

---

## 🛠️ Pré-requisitos

| Componente | Requisito Mínimo | Recomendado |
| :--- | :--- | :--- |
| **Servidor Web** | Apache 2.4+ / Nginx | Apache com `mod_rewrite` ativado |
| **Ambiente Local** | XAMPP v8.0+ | XAMPP para Windows / Linux / macOS |
| **Linguagem** | PHP 7.4 | PHP 8.0 ou superior |
| **Banco de Dados** | MySQL 5.7 / MariaDB 10.2 | MySQL 8.0+ / MariaDB 10.5+ |
| **Extensões PHP** | `pdo_mysql`, `gd`, `curl` | `pdo_mysql`, `gd`, `curl`, `mbstring` |

---

## 🚀 Instalação e Configuração

### 🖥️ Opção 1: Instalação Online (Servidor Web / Hospedagem / VPS)

1. **Upload dos Arquivos:**
   * Envie a pasta do projeto para o diretório raiz da sua hospedagem (ex: `public_html/alfa_saude` ou subdomínio `saude.seudominio.com.br`) via Gerenciador de Arquivos do cPanel ou FTP (FileZilla).

2. **Criação e Importação do Banco de Dados:**
   * Acesse o **phpMyAdmin** ou o assistente de banco de dados do cPanel.
   * Crie um banco de dados com codificação `utf8mb4_unicode_ci` (ex: `usuario_alfa_saude`).
   * Crie um usuário de banco de dados, atribua todas as permissões e anote a senha.
   * Vá na aba **Importar**, selecione o arquivo `banco.sql` localizado na raiz do projeto e clique em **Executar**.

3. **Configuração de Conexão:**
   * Edite o arquivo `config/database.php` com os dados do seu servidor de hospedagem:
     ```php
     <?php
     // config/database.php
     $host     = 'localhost'; // Ou IP/Host do seu servidor MySQL
     $dbname   = 'usuario_alfa_saude';
     $username = 'usuario_banco';
     $password = 'SuaSenhaForte123!';

     try {
         $pdo = new PDO("mysql:host=$host;dbname=$dbname;charset=utf8mb4", $username, $password);
         $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
     } catch (PDOException $e) {
         die("Erro na conexão com o banco de dados: " . $e->getMessage());
     }
     ```

4. **Permissões de Pastas:**
   * Certifique-se de aplicar permissões de gravação (`755` ou `777`) para os diretórios de mídia:
     ```bash
     chmod -R 755 assets/img/
     chmod -R 755 assets/qrcodes/
     ```

---

### 💻 Opção 2: Instalação Local com XAMPP

1. **Instalação do XAMPP:**
   * Baixe e instale o XAMPP com **PHP 8.0+** em [apachefriends.org](https://www.apachefriends.org/).

2. **Cópia do Projeto:**
   * Mova a pasta do sistema para o diretório `htdocs` da sua instalação do XAMPP:
     * **Windows:** `C:\xampp\htdocs\alfa_saude`
     * **Linux:** `/opt/lampp/htdocs/alfa_saude`
     * **macOS:** `/Applications/XAMPP/htdocs/alfa_saude`

3. **Inicialização dos Serviços:**
   * Abra o **XAMPP Control Panel** e inicie os módulos **Apache** e **MySQL**.

4. **Criação e Importação do Banco de Dados:**
   * Acesse `http://localhost/phpmyadmin` no seu navegador.
   * Crie um novo banco de dados chamado `alfa_saude` (Collation: `utf8mb4_unicode_ci`).
   * Vá na aba **Importar**, selecione o arquivo `banco.sql` do projeto e clique em **Executar**.

5. **Configuração de Conexão:**
   * Ajuste o arquivo `config/database.php` com os padrões do XAMPP:
     ```php
     <?php
     // config/database.php
     $host     = 'localhost';
     $dbname   = 'alfa_saude';
     $username = 'root';
     $password = ''; // No XAMPP a senha padrão vem em branco
     ```

---

## 🔑 Acesso Inicial

Acesse a URL correspondente ao seu ambiente de instalação no navegador:

* 🌐 **Online (Web):** `https://seusite.com.br/alfa_saude/login.php`
* 💻 **Local (XAMPP):** `http://localhost/alfa_saude/login.php`

> **Credenciais Padrão do Administrador:**
> * **E-mail:** `alfa@alfasistemas.dev.br`
> * **Senha:** `alfa123@`

⚠️ **Importante:** Altere a senha do administrador logo no primeiro acesso acessando o menu **Usuários > Editar perfil**.

---

## 📂 Estrutura do Projeto

```text
alfa_saude/
├── assets/
│   ├── css/          # Estilos e temas da aplicação
│   ├── js/           # Scripts front-end
│   ├── img/          # Uploads de imagens e logotipos da clínica
│   └── qrcodes/      # QR Codes gerados dinamicamente
├── config/
│   ├── auth.php      # Controle de sessão e autenticação
│   └── database.php  # Configurações do banco de dados
├── includes/
│   ├── footer.php    # Rodapé padrão
│   ├── sidebar.php   # Menu lateral de navegação
│   └── topbar.php    # Barra superior com atalhos de perfil e tema
├── modules/          # Módulos principais (agendamentos, pacientes, etc.)
├── dashboard.php     # Painel de controle principal
├── login.php         # Tela de autenticação
└── logout.php        # Encerramento de sessão
