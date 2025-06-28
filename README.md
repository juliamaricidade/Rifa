<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rifa - Cesta de Festa Junina!</title>
    <link href="https://fonts.googleapis.com/css2?family=Lobster&family=Open+Sans:wght@400;700&display=swap" rel="stylesheet">
    <style>
        /* Definição de variáveis CSS para facilitar a personalização das cores */
        :root {
            --color-primary: #d9534f; /* Vermelho Junino principal */
            --color-secondary: #f0ad4e; /* Laranja/Amarelo de destaque */
            --color-accent: #5cb85c; /* Verde para sucesso/seleção */
            --color-text: #333; /* Cor padrão do texto */
            --color-bg-light: #fefcf5; /* Fundo geral mais claro */
            --color-bg-dark: #fff8e1; /* Fundo de seções com leve tom amarelado */
            --color-border: #ccc; /* Cor padrão da borda */
        }

        /* Estilos globais para o corpo da página */
        body {
            font-family: 'Open Sans', sans-serif; /* Fonte para o texto geral */
            margin: 0;
            padding: 20px;
            background-color: var(--color-bg-light); /* Fundo claro */
            color: var(--color-text); /* Cor do texto */
            line-height: 1.6; /* Espaçamento entre linhas para melhor leitura */
        }

        /* Contêiner principal para centralizar o conteúdo */
        .container {
            max-width: 960px; /* Largura máxima do conteúdo */
            margin: 20px auto; /* Centraliza o contêiner na página */
            background-color: #fff; /* Fundo branco para o conteúdo */
            padding: 40px;
            border-radius: 12px; /* Cantos arredondados */
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1); /* Sombra suave para profundidade */
            border: 1px solid var(--color-border); /* Borda sutil */
        }

        /* Estilos do cabeçalho da página */
        header {
            text-align: center;
            margin-bottom: 40px;
        }

        /* Título principal da rifa */
        h1 {
            font-family: 'Lobster', cursive; /* Fonte decorativa para o título */
            color: var(--color-primary); /* Cor vermelha junina */
            font-size: 3.5em; /* Tamanho grande do título */
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.1); /* Sombra para o texto do título */
        }

        /* Subtítulo abaixo do título principal */
        .subtitle {
            font-size: 1.2em;
            color: var(--color-text);
            margin-top: -10px; /* Ajusta o espaçamento */
            margin-bottom: 20px;
        }

        /* Títulos de seção (Prêmio Detalhado, Números, etc.) */
        h2 {
            font-family: 'Lobster', cursive; /* Fonte decorativa */
            color: var(--color-accent); /* Cor verde de destaque */
            font-size: 2em;
            border-bottom: 2px solid var(--color-secondary); /* Borda inferior para destaque */
            padding-bottom: 5px;
            margin-top: 40px;
            margin-bottom: 20px;
            text-align: center;
        }

        /* Parágrafos de texto */
        p {
            margin-bottom: 15px;
        }

        /* Lista de itens (do prêmio) */
        ul {
            list-style: none; /* Remove os marcadores padrão da lista */
            padding-left: 0;
            margin-bottom: 20px;
        }

        /* Cada item da lista de prêmios */
        ul li {
            background-color: var(--color-bg-dark); /* Fundo amarelado */
            padding: 10px 15px;
            margin-bottom: 8px;
            border-radius: 6px;
            border: 1px solid #ffe0b2; /* Borda suave */
            display: flex; /* Para alinhar o ícone */
            align-items: center;
            gap: 10px; /* Espaçamento entre o ícone e o texto */
        }

        /* Ícone de milho para cada item da lista (pseudo-elemento) */
        ul li::before {
            content: '🌽'; /* Ícone de milho */
            margin-right: 5px;
            font-size: 1.2em;
        }

        /* Informações de preço e data do sorteio */
        .price-info {
            font-size: 1.4em;
            font-weight: bold;
            text-align: center;
            margin-top: 20px;
            margin-bottom: 30px;
            color: var(--color-secondary);
            background-color: #fff3e0; /* Fundo mais claro */
            padding: 15px 20px;
            border-radius: 8px;
            border: 2px dashed var(--color-secondary); /* Borda tracejada */
            display: inline-block; /* Para o background se ajustar ao conteúdo */
            width: fit-content; /* Largura ajustada ao conteúdo */
            margin-left: auto; /* Centraliza o bloco */
            margin-right: auto; /* Centraliza o bloco */
        }

        /* Contêiner da imagem do prêmio */
        .raffle-image-container {
            text-align: center;
            margin-bottom: 30px;
        }

        /* Estilos da imagem do prêmio */
        .raffle-image {
            max-width: 100%; /* Garante que a imagem se ajuste ao contêiner */
            height: auto; /* Mantém a proporção da imagem */
            border: 5px solid var(--color-secondary); /* Borda colorida */
            border-radius: 10px; /* Cantos arredondados */
            box-shadow: 0 6px 15px rgba(0, 0, 0, 0.2); /* Sombra para destaque */
        }

        /* Contêiner dos números da rifa (Grid) */
        .raffle-numbers {
            display: grid; /* Layout em grade */
            grid-template-columns: repeat(auto-fill, minmax(50px, 1fr)); /* Colunas flexíveis */
            gap: 8px; /* Espaçamento entre os números */
            margin-top: 20px;
            padding: 15px;
            border: 2px solid var(--color-border);
            border-radius: 10px;
            background-color: var(--color-bg-dark);
            max-height: 400px; /* Altura máxima para os números */
            overflow-y: auto; /* Adiciona barra de rolagem se houver muitos números */
        }

        /* Estilo para cada caixa de número */
        .number-box {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 50px; /* Altura fixa para as caixas */
            border: 2px solid var(--color-primary);
            border-radius: 8px;
            background-color: #ffebee; /* Fundo claro para números */
            font-weight: bold;
            font-size: 1.1em;
            transition: all 0.2s ease-in-out; /* Transição suave para efeitos */
            cursor: default; /* Cursor padrão para não clicáveis */
        }

        /* Estilo para números disponíveis (clicáveis) */
        .number-box.available {
            background-color: #e0f2f7; /* Azul claro para disponível */
            border-color: #4a90e2; /* Borda azul */
            color: #1a5e9a; /* Texto azul escuro */
            cursor: pointer; /* Cursor de "mãozinha" para indicar clicável */
        }

        /* Efeito ao passar o mouse em números disponíveis */
        .number-box.available:hover {
            background-color: #b3e5fc;
            transform: scale(1.05); /* Aumenta um pouco o tamanho */
            box-shadow: 0 2px 8px rgba(0,0,0,0.2); /* Sombra ao passar o mouse */
        }

        /* Estilo para números indisponíveis (já ocupados) */
        .number-box.unavailable {
            background-color: #f2dede; /* Vermelho claro para indisponível */
            border-color: #a94442;
            color: #8a6d3b;
            text-decoration: line-through; /* Linha sobre o número */
            cursor: not-allowed; /* Cursor de "proibido" */
            opacity: 0.7; /* Transparência suave */
        }

        /* Estilo para números que foram selecionados pelo usuário */
        .number-box.selected {
            background-color: var(--color-accent); /* Verde de destaque para selecionado */
            border-color: #2e8b57;
            color: white;
            box-shadow: 0 0 10px rgba(0, 128, 0, 0.5); /* Sombra verde */
            transform: scale(1.08); /* Aumenta um pouco mais */
            pointer-events: none; /* Impede novos cliques no número selecionado */
        }

        /* Contêiner para exibir os números selecionados */
        .selected-numbers-display {
            margin-top: 20px;
            padding: 15px;
            background-color: #e6ffe6; /* Fundo verde claro */
            border: 1px dashed var(--color-accent); /* Borda tracejada verde */
            border-radius: 8px;
            display: none; /* Escondido por padrão */
        }
        .selected-numbers-display p {
            margin: 0;
            font-weight: bold;
            color: var(--color-accent);
        }
        .selected-numbers-list {
            display: inline; /* Mantém a lista na mesma linha do texto */
            font-weight: normal;
        }

        /* Seção do formulário de contato */
        .form-section {
            margin-top: 40px;
            padding: 25px;
            background-color: #fff8e1; /* Fundo amarelado para o formulário */
            border: 1px solid var(--color-secondary);
            border-radius: 10px;
            display: none; /* Escondido inicialmente */
        }
        .form-section label {
            display: block; /* Cada label em uma nova linha */
            margin-bottom: 8px;
            font-weight: bold;
            color: var(--color-primary);
        }
        .form-section input[type="text"],
        .form-section input[type="email"],
        .form-section input[type="tel"],
        .form-section textarea {
            width: calc(100% - 20px); /* Largura total menos padding */
            padding: 10px;
            margin-bottom: 15px;
            border: 1px solid var(--color-border);
            border-radius: 5px;
            font-size: 1em;
        }
        .form-section textarea {
            resize: vertical; /* Permite redimensionar verticalmente */
            min-height: 80px;
        }
        .form-section button {
            background-color: var(--color-accent); /* Fundo verde */
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 5px;
            font-size: 1.1em;
            cursor: pointer;
            transition: background-color 0.3s ease; /* Transição para o hover */
            display: block; /* Botão ocupa a largura total */
            width: 100%;
        }
        .form-section button:hover {
            background-color: #4CAF50; /* Verde mais escuro no hover */
        }

        /* Informações de contato geral */
        .contact-info {
            text-align: center;
            margin-top: 30px;
            font-size: 1.1em;
            color: var(--color-primary);
        }
        .contact-info a {
            color: var(--color-primary);
            text-decoration: none;
            font-weight: bold;
        }
        .contact-info a:hover {
            text-decoration: underline;
        }

        /* Rodapé da página */
        .footer {
            text-align: center;
            margin-top: 50px;
            padding-top: 20px;
            border-top: 1px solid #eee; /* Borda superior sutil */
            font-size: 0.9em;
            color: #777;
        }

        /* Estilos para mensagens de feedback (sucesso/erro) */
        .message {
            padding: 15px;
            margin-top: 20px;
            border-radius: 8px;
            font-weight: bold;
            text-align: center;
            display: none; /* Escondido por padrão */
        }
        .message.success {
            background-color: #dff0d8;
            color: #3c763d;
            border: 1px solid #d6e9c6;
        }
        .message.error {
            background-color: #f2dede;
            color: #a94442;
            border: 1px solid #ebccd1;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Rifa: Cesta de Festa Junina!</h1>
            <p class="subtitle">Garanta já a sua chance de levar um super prêmio!</p>
        </header>

        <div class="raffle-image-container">
            <img src="https://i.postimg.cc/28kZPzxq/Screenshot-20250628-091039.png" alt="Cesta de Festa Junina com delícias típicas" class="raffle-image">
        </div>

        <p class="price-info">
            🎉 Cada número é R$10,00<br>
            📅 Sorteio dia 20/07
        </p>

        <h2>Prêmio Detalhado</h2>
        <p>Valendo uma cesta de Festa Junina com diversas delícias! A cesta contém:</p>
        <ul>
            <li>Cocada</li>
            <li>Doce de Leite</li>
            <li>Maçã do Amor</li>
            <li>Pacote de Canjica</li>
            <li>Pacote de Fubá</li>
            <li>Pamonha</li>
            <li>Pé de Moça</li>
            <li>Pé de Moleque</li>
            <li>Pipoca</li>
            <li>Salgadinhos </li>
        </ul>

        <h2>Escolha seu(s) Número(s) da Sorte!</h2>
        <p>Clique nos números disponíveis para selecioná-los. Você pode escolher mais de um!</p>
        <div class="raffle-numbers" id="raffleNumbers">
            </div>

        <div class="selected-numbers-display" id="selectedNumbersDisplay">
            <p>Número(s) selecionado(s): <span class="selected-numbers-list" id="selectedNumbersList"></span></p>
        </div>

        <div class="form-section" id="contactFormSection">
            <h2>Complete sua Participação</h2>
            <p>Para finalizar sua reserva e receber as informações de pagamento, por favor, preencha os dados abaixo:</p>
            <form id="raffleForm">
                <label for="nome">Seu Nome Completo:</label>
                <input type="text" id="nome" name="nome" required placeholder="Ex: Maria da Silva">

                <label for="email">Seu E-mail (opcional):</label>
                <input type="email" id="email" name="email" placeholder="Ex: seuemail@dominio.com">

                <label for="telefone">Seu WhatsApp (com DDD):</label>
                <input type="tel" id="telefone" name="telefone" pattern="[0-9]{10,11}" required placeholder="Ex: 11998765432">
                <small>Formato: Apenas números (DDD + número)</small>

                <label for="observacoes">Observações (opcional):</label>
                <textarea id="observacoes" name="observacoes" placeholder="Alguma observação sobre sua participação?"></textarea>

                <button type="submit">Reservar Meus Números e Entrar em Contato!</button>
            </form>
            <div id="formMessage" class="message"></div>
        </div>

        <div class="contact-info">
            <p>Dúvidas? Fale conosco:</p>
            <p>Organizadora da rifa: Maria Julia</p> <p>📞 <a href="tel:+5518997311604">Ligue agora!</a></p>
            <p>📱 <a id="whatsappLink" href="#" target="_blank">Envie um WhatsApp!</a></p>
        </div>

        <div class="footer">
            <p>&copy; 2025 Sua Rifa. Todos os direitos reservados. Boa sorte!</p>
        </div>
    </div>

    <script>
        const totalNumbers = 120; // Total de números na rifa
        const raffleNumbersDiv = document.getElementById('raffleNumbers');
        const selectedNumbersDisplay = document.getElementById('selectedNumbersDisplay');
        const selectedNumbersList = document.getElementById('selectedNumbersList');
        const contactFormSection = document.getElementById('contactFormSection');
        const raffleForm = document.getElementById('raffleForm');
        const formMessage = document.getElementById('formMessage');
        const whatsappLinkGeral = document.getElementById('whatsappLink'); // Link geral de contato no rodapé

        let selectedNumbers = new Set(); // Usar Set para armazenar números selecionados (garante únicos)
        
        // Simulação de números já ocupados. EM UM SISTEMA REAL, ISSO VIRIA DE UM BANCO DE DADOS/BACKEND.
        // Adicione aqui os números que JÁ FORAM CONFIRMADOS como vendidos.
        const permanentlyUnavailableNumbers = new Set([]); // AGORA VAZIA, NENHUM NÚMERO RISCADO POR PADRÃO!

        // SEU NÚMERO DE WHATSAPP PARA RECEBER AS RESERVAS (apenas números, com DDD. Ex: 5511999999999)
        const yourPhoneNumber = '5518997311604'; // SEU NÚMERO AQUI!

        // Função para gerar e exibir os números da rifa no grid
        function generateRaffleNumbers() {
            raffleNumbersDiv.innerHTML = ''; // Limpa o conteúdo existente
            for (let i = 1; i <= totalNumbers; i++) {
                const numberBox = document.createElement('div');
                numberBox.classList.add('number-box');
                numberBox.textContent = i;
                numberBox.dataset.number = i; // Armazena o número como um atributo de dado

                if (permanentlyUnavailableNumbers.has(i)) {
                    // Se o número já está permanentemente indisponível
                    numberBox.classList.add('unavailable');
                } else if (selectedNumbers.has(i)) {
                    // Se o número foi temporariamente selecionado pelo usuário
                    numberBox.classList.add('selected');
                } else {
                    // Se o número está disponível para seleção
                    numberBox.classList.add('available');
                    numberBox.addEventListener('click', toggleNumberSelection); // Adiciona evento de clique
                }
                raffleNumbersDiv.appendChild(numberBox);
            }
        }

        // Função para alternar a seleção de um número ao clicar
        function toggleNumberSelection(event) {
            const numberBox = event.target;
            const number = parseInt(numberBox.dataset.number); // Pega o número do dataset

            if (permanentlyUnavailableNumbers.has(number)) {
                // Não faz nada se o número for permanentemente indisponível
                return; 
            }

            if (selectedNumbers.has(number)) {
                // Se o número já estava selecionado, deseleciona
                selectedNumbers.delete(number);
                numberBox.classList.remove('selected');
                numberBox.classList.add('available');
            } else {
                // Se o número não estava selecionado, seleciona
                selectedNumbers.add(number);
                numberBox.classList.add('selected');
                numberBox.classList.remove('available');
            }
            updateSelectedNumbersDisplay(); // Atualiza a exibição dos números selecionados
            toggleFormVisibility(); // Mostra/esconde o formulário
        }

        // Função para atualizar a lista de números selecionados exibida ao usuário
        function updateSelectedNumbersDisplay() {
            if (selectedNumbers.size > 0) {
                const sortedNumbers = Array.from(selectedNumbers).sort((a, b) => a - b); // Ordena os números
                selectedNumbersList.textContent = sortedNumbers.join(', '); // Exibe separados por vírgula
                selectedNumbersDisplay.style.display = 'block'; // Mostra a div de exibição
            } else {
                selectedNumbersList.textContent = '';
                selectedNumbersDisplay.style.display = 'none'; // Esconde a div de exibição
            }
        }

        // Função para mostrar ou esconder a seção do formulário de contato
        function toggleFormVisibility() {
            if (selectedNumbers.size > 0) {
                contactFormSection.style.display = 'block'; // Mostra o formulário
            } else {
                contactFormSection.style.display = 'none'; // Esconde o formulário
                formMessage.style.display = 'none'; // Esconde qualquer mensagem de feedback do formulário
            }
        }

        // Event Listener para o envio do formulário
        raffleForm.addEventListener('submit', function(event) {
            event.preventDefault(); // Previne o comportamento padrão de recarregar a página

            const nome = document.getElementById('nome').value.trim();
            const email = document.getElementById('email').value.trim();
            const telefone = document.getElementById('telefone').value.trim();
            const observacoes = document.getElementById('observacoes').value.trim();
            const selectedNumbersArray = Array.from(selectedNumbers).sort((a, b) => a - b);

            // Validações básicas
            if (selectedNumbersArray.length === 0) {
                displayMessage(formMessage, 'Por favor, selecione pelo menos um número da rifa.', 'error');
                return;
            }

            if (!nome || !telefone) {
                displayMessage(formMessage, 'Nome e WhatsApp são campos obrigatórios.', 'error');
                return;
            }

            // Monta a mensagem para o WhatsApp
            const raffleName = "Cesta de Festa Junina";
            let message = `Olá! Tenho interesse na Rifa da ${raffleName}.\n`;
            message += `Meu nome é: ${nome}\n`;
            if (email) message += `Meu e-mail é: ${email}\n`;
            message += `Meu WhatsApp é: ${telefone}\n`;
            message += `Gostaria de reservar o(s) número(s): ${selectedNumbersArray.join(', ')}\n`;
            message += `Valor total: R$${(selectedNumbersArray.length * 10).toFixed(2).replace('.', ',')}\n`; // Formata para BRL
            if (observacoes) message += `Observações: ${observacoes}\n`;
            message += `Aguardando informações para o pagamento e confirmação!`;

            // Codifica a mensagem para URL
            const whatsappUrl = `https://wa.me/${yourPhoneNumber}?text=${encodeURIComponent(message)}`;

            // Abre o WhatsApp em uma nova aba/janela
            window.open(whatsappUrl, '_blank');

            // Feedback visual para o usuário
            displayMessage(formMessage, 'Seu interesse foi registrado! Abrindo o WhatsApp para finalizarmos sua reserva. Por favor, confirme a mensagem lá.', 'success');
            
            // SIMULAÇÃO: Marca os números como indisponíveis NA SESSÃO DO NAVEGADOR
            // Em uma aplicação real, isso seria feito APÓS A CONFIRMAÇÃO DO PAGAMENTO NO BACKEND.
            selectedNumbers.forEach(num => permanentlyUnavailableNumbers.add(num));
            selectedNumbers.clear(); // Limpa a seleção atual
            generateRaffleNumbers(); // Redesenha os números para atualizar o status
            updateSelectedNumbersDisplay(); // Esconde a exibição de números selecionados
            raffleForm.reset(); // Limpa os campos do formulário
            // contactFormSection.style.display = 'none'; // Se quiser esconder o formulário imediatamente
            toggleFormVisibility(); // Esconde o formulário se não houver mais números selecionados
        });

        // Função auxiliar para exibir mensagens de feedback
        function displayMessage(element, text, type) {
            element.textContent = text;
            element.className = 'message ' + type; // Define a classe para o estilo (success ou error)
            element.style.display = 'block';
            // Rola a página para a mensagem para garantir que ela esteja visível
            element.scrollIntoView({ behavior: 'smooth', block: 'center' });
        }

        // Define o link do WhatsApp para o contato geral no rodapé
        whatsappLinkGeral.href = `https://wa.me/${yourPhoneNumber}?text=${encodeURIComponent("Olá! Gostaria de saber mais sobre a Rifa da Cesta de Festa Junina.")}`;


        // Chama a função para gerar os números da rifa quando a página é carregada
        generateRaffleNumbers();
    </script>
</body>
</html>
