<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TravelDream - Sua Agência de Viagens</title>
    <style>
        /* Reset e configurações básicas */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
        }

        /* Header e Navegação */
        header {
            background: #2c3e50;
            color: white;
            padding: 1rem 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #3498db;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 5px;
        }

        .nav-links a:hover {
            color: #3498db;
            background: rgba(255, 255, 255, 0.1);
        }

        /* Banner Principal */
        .banner {
            height: 100vh;
            background: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)), 
                        url('https://img.freepik.com/fotos-gratis/tendencias-de-viagem-2024_23-2150629657.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            color: white;
            margin-top: 60px;
        }

        .banner-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        .banner-content p {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.5);
        }

        .cta-button {
            display: inline-block;
            background: #3498db;
            color: white;
            padding: 1rem 2rem;
            text-decoration: none;
            border-radius: 5px;
            transition: background 0.3s ease, transform 0.3s ease;
            font-weight: bold;
        }

        .cta-button:hover {
            background: #2980b9;
            transform: translateY(-2px);
        }

        /* Seções */
        section {
            padding: 5rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            color: #2c3e50;
            font-size: 2.5rem;
        }

        /* TripMe Section */
        #tripme {
            background: #f8f9fa;
        }

        .destinos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .destino-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s ease;
        }

        .destino-card:hover {
            transform: translateY(-5px);
        }

        .destino-img {
            width: 100%;
            height: 250px;
            object-fit: cover;
        }

        .destino-content {
            padding: 1.5rem;
        }

        .destino-content h3 {
            color: #2c3e50;
            margin-bottom: 1rem;
        }

        /* MeetUs Section */
        #meetus {
            background: white;
        }

        .equipe {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .membro {
            text-align: center;
            padding: 2rem;
            background: #f8f9fa;
            border-radius: 10px;
            transition: background 0.3s ease;
        }

        .membro:hover {
            background: #e9ecef;
        }

        .membro-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            margin-bottom: 1rem;
            border: 5px solid #3498db;
        }

        /* Advice Section */
        #advice {
            background: #34495e;
            color: white;
        }

        .conselhos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .conselho {
            background: rgba(255, 255, 255, 0.1);
            padding: 2rem;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s ease;
        }

        .conselho:hover {
            transform: scale(1.05);
        }

        .conselho h3 {
            margin-bottom: 1rem;
            color: #3498db;
        }

        /* Galeria de Fotos */
        .galeria-fotos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1rem;
            margin-top: 2rem;
        }

        .foto-item {
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            transition: transform 0.3s ease;
        }

        .foto-item:hover {
            transform: scale(1.05);
        }

        .foto-item img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1rem;
        }

        .footer-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: #3498db;
        }

        /* Responsividade */
        @media (max-width: 768px) {
            .nav-links {
                flex-direction: column;
                gap: 1rem;
            }

            .banner-content h1 {
                font-size: 2.5rem;
            }

            section {
                padding: 3rem 1rem;
            }

            .footer-links {
                flex-direction: column;
                gap: 1rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header e Navegação -->
    <header>
        <nav>
            <div class="logo">TravelDream</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#tripme">TripMe</a></li>
                <li><a href="#meetus">MeetUs</a></li>
                <li><a href="#advice">Advice</a></li>
            </ul>
        </nav>
    </header>

    <!-- Banner Principal -->
    <main>
        <section id="home" class="banner">
            <div class="banner-content">
                <h1>Descubra o Mundo Conosco</h1>
                <p>Experiências únicas que ficarão para sempre na sua memória</p>
                <a href="#tripme" class="cta-button">Explorar Destinos</a>
            </div>
        </section>

        <!-- Seção TripMe -->
        <section id="tripme">
            <h2 class="section-title">TripMe - Nossos Destinos</h2>
            <div class="destinos">
                <div class="destino-card">
                    <img src="https://img.freepik.com/fotos-gratis/tendencias-de-viagem-2024_23-2150629657.jpg" 
                         alt="Tendências de viagem 2024 - paisagem deslumbrante" class="destino-img">
                    <div class="destino-content">
                        <h3>Destinos 2024</h3>
                        <p>Explore as tendências de viagem do ano com destinos exclusivos e experiências únicas.</p>
                    </div>
                </div>
                <div class="destino-card">
                    <img src="https://img.freepik.com/fotos-gratis/fotografar-viagem-veja-dicas-para-tirar-fotos-incriveis_23-2150698655.jpg" 
                         alt="Dicas para fotografar viagens - paisagem incrível" class="destino-img">
                    <div class="destino-content">
                        <h3>Fotografia de Viagem</h3>
                        <p>Aprenda a capturar momentos especiais com nossas dicas de fotografia profissional.</p>
                    </div>
                </div>
                <div class="destino-card">
                    <img src="https://img.freepik.com/fotos-gratis/como-tirar-fotos-de-viagem-um-guia-pratico-para-cliques-inclriveis-mulher-fotografando-paisagem_23-2150698658.jpg" 
                         alt="Mulher fotografando paisagem - guia prático" class="destino-img">
                    <div class="destino-content">
                        <h3>Guias Práticos</h3>
                        <p>Descubra os melhores ângulos e técnicas para fotos impressionantes em suas viagens.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção MeetUs -->
        <section id="meetus">
            <h2 class="section-title">MeetUs - Nossa Equipe</h2>
            <div class="equipe">
                <div class="membro">
                    <img src="https://img.freepik.com/fotos-gratis/tendencias-de-viagem-2024_23-2150629657.jpg" 
                         alt="Especialista em destinos - João" class="membro-img">
                    <h3>João Silva</h3>
                    <p>Especialista em Destinos</p>
                    <p>Conhece os lugares mais incríveis para suas próximas aventuras.</p>
                </div>
                <div class="membro">
                    <img src="https://img.freepik.com/fotos-gratis/fotografar-viagem-veja-dicas-para-tirar-fotos-incriveis_23-2150698655.jpg" 
                         alt="Fotógrafa profissional - Maria" class="membro-img">
                    <h3>Maria Santos</h3>
                    <p>Fotógrafa Profissional</p>
                    <p>Ensina técnicas incríveis para registrar suas melhores memórias.</p>
                </div>
                <div class="membro">
                    <img src="https://img.freepik.com/fotos-gratis/como-tirar-fotos-de-viagem-um-guia-pratico-para-cliques-inclriveis-mulher-fotografando-paisagem_23-2150698658.jpg" 
                         alt="Consultora de viagens - Ana" class="membro-img">
                    <h3>Ana Costa</h3>
                    <p>Consultora de Viagens</p>
                    <p>Ajuda a planejar cada detalhe da sua jornada perfeita.</p>
                </div>
            </div>

            <!-- Galeria de Fotos da Equipe em Ação -->
            <div style="margin-top: 4rem;">
                <h3 style="text-align: center; margin-bottom: 2rem; color: #2c3e50;">Nossa Equipe em Ação</h3>
                <div class="galeria-fotos">
                    <div class="foto-item">
                        <img src="https://img.freepik.com/fotos-gratis/tendencias-de-viagem-2024_23-2150629657.jpg" 
                             alt="Tendências de viagem 2024">
                    </div>
                    <div class="foto-item">
                        <img src="https://img.freepik.com/fotos-gratis/fotografar-viagem-veja-dicas-para-tirar-fotos-incriveis_23-2150698655.jpg" 
                             alt="Dicas para fotos incríveis">
                    </div>
                    <div class="foto-item">
                        <img src="https://img.freepik.com/fotos-gratis/como-tirar-fotos-de-viagem-um-guia-pratico-para-cliques-inclriveis-mulher-fotografando-paisagem_23-2150698658.jpg" 
                             alt="Guia prático para fotos">
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção Advice -->
        <section id="advice">
            <h2 class="section-title">Advice - Nossos Conselhos</h2>
            <div class="conselhos">
                <div class="conselho">
                    <h3>📸 Fotografia</h3>
                    <p>Aproveite a luz natural do amanhecer e entardecer para fotos espetaculares. Use a regra dos terços para composições mais interessantes.</p>
                </div>
                <div class="conselho">
                    <h3>🎒 Preparação</h3>
                    <p>Pesquise sobre a cultura local e clima do destino. Faça uma lista de verificação para não esquecer itens importantes.</p>
                </div>
                <div class="conselho">
                    <h3>💰 Orçamento</h3>
                    <p>Planeje seu orçamento incluindo 15% para imprevistos. Reserve com antecedência para melhores preços.</p>
                </div>
                <div class="conselho">
                    <h3>🌍 Sustentabilidade</h3>
                    <p>Respeite o meio ambiente e a cultura local. Prefira acomodações e serviços com práticas sustentáveis.</p>
                </div>
            </div>

            <!-- Dicas Extras de Fotografia -->
            <div style="margin-top: 4rem;">
                <h3 style="text-align: center; margin-bottom: 2rem; color: #3498db;">Dicas de Fotografia para Viagens</h3>
                <div class="conselhos">
                    <div class="conselho">
                        <h3>Ângulos Criativos</h3>
                        <p>Experimente diferentes perspectivas: de baixo para cima, close-ups em detalhes, e paisagens amplas.</p>
                    </div>
                    <div class="conselho">
                        <h3>Equipamento Essencial</h3>
                        <p>Leve tripé para fotos noturnas, lentes extras e baterias de reserva. Não esqueça os cartões de memória!</p>
                    </div>
                    <div class="conselho">
                        <h3>Edição Básica</h3>
                        <p>Aprenda ajustes simples como correção de exposição, contraste e saturação para realçar suas fotos.</p>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="footer-links">
            <a href="#home">Home</a>
            <a href="#tripme">TripMe</a>
            <a href="#meetus">MeetUs</a>
            <a href="#advice">Advice</a>
        </div>
        <p>&copy; 2024 TravelDream. Todos os direitos reservados.</p>
        <p>Transformando sonhos em experiências inesquecíveis através das lentes e das paisagens.</p>
    </footer>
</body>
</html>
