
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background: linear-gradient(to bottom right, #6BAED6, #00509E);
            height: 100vh;
            display: flex;
        }

        .login-container {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(15px);
            padding: 30px 40px;
            border-radius: 20px;
            box-shadow: 0px 8px 15px rgba(0, 0, 0, 0.3);
            text-align: center;
            color: white;
            width: 350px;
        }

        .login-container h2 {
            margin-bottom: 20px;
            font-size: 28px;
            font-weight: bold;
        }

        .login-container input {
            width: 100%;
            padding: 12px;
            margin-bottom: 20px;
            border: none;
            border-radius: 8px;
            background: rgba(255, 255, 255, 0.3);
            color: white;
            font-size: 16px;
        }

        .login-container input::placeholder {
            color: white;
            opacity: 0.8;
        }

        .login-container button {
            display: block;
            margin: 0 auto;
            width: 106%;
            padding: 12px;
            background: linear-gradient(to right, #6BAED6, #00509E);
            color: white;
            font-size: 16px;
            font-weight: bold;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            transition: background 0.3s ease;
        }

        .login-container button:hover {
            background: linear-gradient(to right, #00509E, #003a70);
        }

        .login-container form {
            display: flex;
            flex-direction: column;
            gap: 15px;
        }

        .login-container input:focus {
            outline: none;
            box-shadow: 0px 0px 10px rgba(255, 255, 255, 0.7);
        }
    </style>
    <script>
        // Criptografando o nome de usuário e senha esperados (em Base64 para simplicidade)
        const encryptedUsername = btoa("Midland"); // Criptografa "Midland"
        const encryptedPassword = btoa("senha123"); // Criptografa "senha123"

        // Evento de submissão do formulário
        document.addEventListener('DOMContentLoaded', () => {
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
                    alert("Nome de utilizador ou palavra-passe incorretos.");
                }
            });
        });
    </script>
</head>
<body>
    <div class="login-container">
        <h2>Autenticação</h2>
        <form id="loginForm">
            <input type="text" id="username" placeholder="Nome de utilizador" required>
            <input type="password" id="password" placeholder="Palavra-passe" required>
            <button type="submit">Entrar</button>
        </form>
    </div>
</body>
</html>
