<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f1f1f1;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .container {
            background-color: #fff;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 400px;
            text-align: center;
        }

        h1 {
            color: #007bff;
            margin-bottom: 20px;
        }

        label {
            display: block;
            text-align: left;
            margin-bottom: 5px;
            font-size: 14px;
            color: #555;
        }

        input[type="text"],
        input[type="password"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
        }

        button {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            cursor: pointer;
            border: none;
            border-radius: 4px;
        }

        .btn-submit {
            background-color: #007bff;
            color: white;
        }

        .btn-submit:hover {
            background-color: #0056b3;
        }

        .btn-recover {
            background: none;
            color: #007bff;
            text-decoration: underline;
            margin-top: 20px;
            border: none;
            cursor: pointer;
        }

        .error {
            color: red;
            margin-bottom: 10px;
            font-size: 14px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Autenticação</h1>
        <form id="loginForm">
            <label for="username">UTILIZADOR *</label>
            <input type="text" id="username" name="username" placeholder="nome de utilizador" required>

            <label for="password">PALAVRA-PASSE / CÓDIGO DE ACESSO *</label>
            <input type="password" id="password" name="password" placeholder="palavra-passe/código de acesso" required>

            <div class="error" id="errorMessage"></div>

            <button type="submit" class="btn-submit">iniciar sessão</button>
        </form>

        <button class="btn-recover">RECUPERAR ACESSO</button>
    </div>

    <script>
        // Criptografando o nome de usuário e senha esperados (em Base64 para simplicidade)
        const encryptedUsername = btoa("Midland"); // "Midland" -> Base64
        const encryptedPassword = btoa("senha123"); // "senha123" -> Base64

        // Evento de submissão do formulário
        document.getElementById('loginForm').addEventListener('submit', function(event) {
            event.preventDefault(); // Impede o comportamento padrão do formulário

            // Obtém os valores de entrada do usuário
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            // Criptografa os valores fornecidos pelo usuário
            const userEncrypted = btoa(username);
            const passEncrypted = btoa(password);

            // Compara os valores criptografados
            if (userEncrypted === encryptedUsername && passEncrypted === encryptedPassword) {
                // Redireciona para o site desejado
                window.location.href = 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTTwoC8x_iamqeVxwdx_9pgHAFCIyHqllEg-A&s'; // Substitua pelo URL desejado
            } else {
                // Exibe mensagem de erro
                document.getElementById('errorMessage').textContent = 'Nome de utilizador ou palavra-passe incorretos.';
            }
        });
    </script>
</body>
</html>
