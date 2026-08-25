===============================================================================
                     ALFA SAÚDE - SISTEMA DE GESTÃO CLÍNICA
                         
===============================================================================

1. REQUISITOS DO SISTEMA
   - Servidor web Apache (recomendado) ou Nginx
   - PHP 7.4 ou superior (recomenda-se PHP 8.0+)
   - Extensões PHP: PDO, MySQL, GD (para imagens), cURL (opcional)
   - MySQL 5.7 ou MariaDB 10.2+
   - Permissão de escrita nas pastas: assets/img/, assets/qrcodes/

2. BANCO DE DADOS
   - Acesse o phpMyAdmin ou linha de comando do MySQL.
   - Crie um banco de dados com o nome desejado (ex: `alfa_saude`).
   - Importe o arquivo `banco.sql` (fornecido junto com o sistema) para criar as tabelas e inserir os dados iniciais.
   - O arquivo `banco.sql` já contém:
        * Tabelas: clinica, usuarios, pacientes, agendamentos, prontuarios, receituarios, declaracoes, progresso_paciente, logs_acesso.
        * Registro padrão da clínica (Alfa Saúde).
        * Usuário administrador com e-mail `alfa@alfasistemas.dev.br` e senha `alfa123@`.

   Caso prefira criar manualmente, execute os comandos SQL presentes no arquivo `banco.sql`.

3. CONFIGURAÇÃO DOS ARQUIVOS
   - Edite o arquivo `/config/database.php` com as credenciais do seu banco de dados:
        $host = 'localhost';
        $dbname = 'nome_do_banco';
        $username = 'usuario_do_banco';
        $password = 'senha_do_banco';

   - Verifique se as pastas `assets/img/` e `assets/qrcodes/` existem e têm permissão de escrita (chmod 755 ou 777).

4. ACESSO AO SISTEMA
   - Após configurar o banco e os arquivos, acesse o sistema pelo navegador:
        http://seusite.com/alfa_saude/login.php

   - Use as credenciais padrão:
        E-mail: alfa@alfasistemas.dev.br
        Senha:  alfa123@

   - Recomenda-se alterar a senha do administrador no primeiro acesso (através do menu Usuários > editar o próprio usuário).

5. ESTRUTURA DE DIRETÓRIOS (resumo)
   /alfa_saude/
   ├── assets/          (CSS, JavaScript, imagens, QR Codes)
   ├── config/          (database.php, auth.php)
   ├── includes/        (sidebar.php, topbar.php, footer.php)
   ├── modules/         (agendamentos, pacientes, prontuarios, etc.)
   ├── dashboard.php
   ├── login.php
   ├── logout.php
   └── ...

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








