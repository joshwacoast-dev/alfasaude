<div align="center">

# 🏥 Alfa Saúde — Sistema de Gestão Clínica

[![PHP](https://img.shields.io/badge/PHP-8.0%2B-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://www.php.net/)
[![MySQL](https://img.shields.io/badge/MySQL-5.7%2B-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![XAMPP](https://img.shields.io/badge/XAMPP-Supported-FB7A24?style=for-the-badge&logo=xampp&logoColor=white)](https://www.apachefriends.org/)
[![License](https://img.shields.io/badge/License-Proprietary-red?style=for-the-badge)](#)

Sistema web completo para gestão integrada de clínicas, agendamentos, prontuários eletrônicos e controle de pacientes.

[Visitar Website](https://alfasistemas.dev.br) • [Reportar Bug](https://alfasistemas.dev.br) • [Solicitar Recurso](https://alfasistemas.dev.br)

</div>

---

## 📌 Índice
- [Recursos do Sistema](#-recursos-do-sistema)
- [Pré-requisitos](#-pré-requisitos)
- [Instalação e Configuração](#-instalação-e-configuração)
  - [Opção A: Ambiente Local com XAMPP (Recomendado para Testes/Dev)](#opção-a-ambiente-local-com-xampp-recomendado-para-testesdev)
  - [Opção B: Servidor Web / Hospedagem](#opção-b-servidor-web--hospedagem)
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
| **Servidor Local** | XAMPP (com PHP 7.4+) | XAMPP para Windows/Linux/macOS |
| **Servidor Web** | Apache / Nginx | Apache 2.4+ com `mod_rewrite` |
| **Linguagem** | PHP 7.4 | PHP 8.0 ou superior |
| **Banco de Dados** | MySQL 5.7 / MariaDB 10.2 | MySQL 8.0+ / MariaDB 10.5+ |
| **Extensões PHP** | `pdo_mysql`, `gd`, `curl` | `pdo_mysql`, `gd`, `curl`, `mbstring` |

---

## 🚀 Instalação e Configuração

### Opção A: Ambiente Local com XAMPP (Recomendado para Testes/Dev)

1. **Baixe e Instale o XAMPP:**
   Acesse [apachefriends.org](https://www.apachefriends.org/) e instale a versão com **PHP 8.0 ou superior**.
2. **Copie o Projeto:**
   Mova a pasta do sistema para o diretório `htdocs` do XAMPP:
   * Windows: `C:\xampp\htdocs\alfa_saude`
   * Linux: `/opt/lampp/htdocs/alfa_saude`
3. **Inicie os Serviços:**
   Abra o **XAMPP Control Panel** e inicie os módulos **Apache** e **MySQL**.
4. **Crie o Banco de Dados:**
   * Acesse `http://localhost/phpmyadmin` no navegador.
   * Crie um banco de dados chamado `alfa_saude` (Collation: `utf8mb4_unicode_ci`).
   * Vá na aba **Importar**, selecione o arquivo `banco.sql` do repositório e clique em **Executar**.
5. **Configuração de Conexão:**
   Ajuste o arquivo `config/database.php` para as credenciais padrão do XAMPP:
   ```php
   $host     = 'localhost';
   $dbname   = 'alfa_saude';
   $username = 'root';
   $password = ''; // Padrão do XAMPP é sem senha

5. ESTRUTURA DE DIRETÓRIOS (resumo)
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

6. PERSONALIZAÇÃO
   - As cores do sistema podem ser alteradas no menu Clínica (após login como admin).
   - O logo da clínica também pode ser enviado por lá.
   - O tema escuro pode ser ativado pelo botão no canto superior direito.

7. SOLUÇÃO DE PROBLEMAS COMUNS
   - Erro de conexão: verifique as credenciais em `database.php` e se o MySQL está ativo.
   - Página em branco: ative a exibição de erros no PHP (edite o arquivo e adicione `ini_set('display_errors', 1);` no início).
   - Upload de logo não funciona: verifique permissões da pasta `assets/img/` (deve ser gravável).
   - QR Code não aparece: certifique-se de que a pasta `assets/qrcodes/` existe e tem permissão de escrita.

8. SUPORTE
   - Em caso de dúvidas, entre em contato pelo e-mail: suporte@alfasistemas.dev.br
   - Telefone: (85) 2028-4584
   - Site: https://alfasistemas.dev.br


     
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1be75638-c7b6-4fbe-8019-df32b87f2ecb" /><img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/b87f8796-567d-458e-acfd-bddaa01b2d27" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/6a1e6c83-2fef-4cb2-bb71-c4b9aa8656d3" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/930b97b7-ab75-45ea-a134-366effe68f3a" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/9a5a6b19-c9b3-4a9f-a9f2-e38ca27f36b2" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/1f0670a1-ec87-47c8-b867-81047259a6cd" />
<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/e16ec72c-fb29-4c23-a79e-7f4fe1d4cabe" /><img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/492675c4-74ca-42ca-92bc-a7f4f9fc9fef" />








