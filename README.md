<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LexdigestGlobal</title>
    <style>
        :root {
            --text-main: #111;
            --bg-main: #fcfcfc;
            --border-color: #000;
            --accent-blue: #1c3b7a; 
        }
        
        body {
            font-family: 'Georgia', 'Times New Roman', Times, serif;
            color: var(--text-main);
            background-color: var(--bg-main);
            margin: 0;
            padding: 0;
            line-height: 1.6;
        }

        header {
            text-align: center;
            padding: 30px 20px 10px;
            border-bottom: 3px solid var(--border-color);
            max-width: 1200px;
            margin: 0 auto;
        }

        h1.logo {
            font-size: 4.5rem;
            margin: 0;
            letter-spacing: -1.5px;
            font-weight: normal;
            cursor: pointer; /* Makes it look clickable */
        }

        nav {
            display: flex;
            justify-content: center;
            gap: 40px;
            padding: 15px 0;
            border-bottom: 1px solid #ccc;
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            font-weight: bold;
            font-size: 1.1rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        nav a {
            text-decoration: none;
            color: var(--text-main);
            cursor: pointer;
            transition: color 0.2s;
        }

        nav a:hover {
            color: var(--accent-blue);
        }

        main {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        section {
            display: none; 
            animation: fadeIn 0.4s ease-in;
        }

        section.active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Home Layout */
        .home-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 40px;
            align-items: center;
        }

        .home-text {
            flex: 1;
            min-width: 300px;
            font-size: 1.35rem;
            font-weight: bold;
            text-align: center;
            padding: 20px;
        }

        .home-image-container {
            flex: 1;
            min-width: 300px;
            display: flex;
            justify-content: center;
        }

        /* This is how you insert your image later */
        .home-image-container img {
            max-width: 100%;
            height: auto;
            border: 1px solid #ccc; /* Optional border */
        }

        /* Placeholder style just for viewing before you add the image */
        .img-placeholder {
            background-color: var(--accent-blue);
            color: white;
            padding: 80px 40px;
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            font-size: 3.5rem;
            font-weight: 900;
            line-height: 1;
            text-transform: uppercase;
            width: 100%;
            text-align: left;
            box-sizing: border-box;
        }

        /* Journal Layout */
        .journal-header {
            text-align: center;
            margin-bottom: 40px;
        }

        .journal-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
        }

        .article-card {
            border-top: 2px solid var(--border-color);
            padding-top: 15px;
        }

        .article-category {
            font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
            font-size: 0.8rem;
            text-transform: uppercase;
            color: #666;
            margin-bottom: 5px;
        }

        .article-card h2 {
            font-size: 1.8rem;
            margin: 0 0 10px 0;
            line-height: 1.2;
        }

        /* Advisory & Tool Layout */
        .content-wrapper {
            max-width: 800px;
            margin: 0 auto;
        }
        
        .content-wrapper h2 {
            font-size: 2.5rem;
            border-bottom: 1px solid #ccc;
            padding-bottom: 10px;
        }

        .tool-wrapper {
            background: #fff;
            border: 1px solid #ccc;
            padding: 30px;
            box-shadow: 0 4px 6px rgba(0,0,0,0.05);
            margin-top: 40px;
        }

        .tool-wrapper label {
            display: block;
            font-family: sans-serif;
            font-weight: bold;
            margin-top: 20px;
            margin-bottom: 5px;
        }

        .tool-wrapper select {
            width: 100%;
            padding: 10px;
            font-size: 1rem;
            border: 1px solid #ccc;
            font-family: sans-serif;
        }

        .tool-wrapper button {
            width: 100%;
            background: var(--text-main);
            color: #fff;
            border: none;
            padding: 15px;
            font-size: 1.2rem;
            font-family: sans-serif;
            font-weight: bold;
            margin-top: 30px;
            cursor: pointer;
        }

        .tool-wrapper button:hover {
            background: var(--accent-blue);
        }

        #tool-result {
            margin-top: 30px;
            padding: 20px;
            background: #f4f6f9;
            border-left: 4px solid var(--accent-blue);
            display: none;
        }

        /* Contact Form */
        .contact-form {
            display: flex;
            flex-direction: column;
            gap: 15px;
            font-family: sans-serif;
        }

        .contact-form input, .contact-form textarea {
            width: 100%;
            padding: 10px;
            border: 1px solid #ccc;
            font-size: 1rem;
            box-sizing: border-box;
        }

        .contact-form button {
            background: var(--text-main);
            color: #fff;
            border: none;
            padding: 15px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
        }

    </style>
</head>
<body>

    <header>
        <h1 class="logo" onclick="showSection('home')">LexdigestGlobal</h1>
    </header>

    <nav>
        <a onclick="showSection('advisory')">Advisory</a>
        <a onclick="showSection('journals')">Journals</a>
        <a onclick="showSection('contact')">Contact</a>
        <a onclick="showSection('impressum')">Impressum</a>
    </nav>

    <main>
        <section id="home" class="active">
            <div class="home-grid">
                <div class="home-text">
                    <p>We translate global complexity into local action.<br>
                    LexdigestGlobal is a hybrid intelligence platform designed to educate.</p>
                    <p>We provide deep-dive journalistic insights into shifting geopolitical power structures, paired with a strategic advisory hub that navigates SMEs through the intricacies of EU funding, regulatory compliance, and international expansion.</p>
                </div>
                <div class="home-image-container">
                    <div class="img-placeholder">
                        PROTECT<br>WHAT<br>MATTERS.
                    </div>
                </div>
            </div>
        </section>

        <section id="journals">
            <div class="journal-header">
                <h2 style="font-size: 2.5rem; margin-bottom: 0;">Intelligence & Analysis</h2>
                <p style="font-family: sans-serif; color: #555;">In-depth reporting on geopolitics, corporate strategy, and regulatory shifts.</p>
            </div>
            <div class="journal-grid">
                <article class="article-card">
                    <div class="article-category">Geopolitics</div>
                    <h2>The Shifting Supply Chains: Why Nearshoring is the New Normal</h2>
                    <p>An in-depth look at how recent geopolitical tensions are forcing European SMEs to rethink their reliance on distant manufacturing hubs...</p>
                </article>
                <article class="article-card">
                    <div class="article-category">Corporate Strategy</div>
                    <h2>Surviving the Tech Cold War: A Guide for Medium Enterprises</h2>
                    <p>As superpowers clash over semiconductor dominance, how can your software architecture remain resilient and independent?</p>
                </article>
                <article class="article-card">
                    <div class="article-category">Regulatory Compliance</div>
                    <h2>The EU AI Act: Bureaucratic Nightmare or Competitive Advantage?</h2>
                    <p>Decoding the complexities of the latest Brussels legislation and how smart SMEs can use compliance as a unique selling proposition.</p>
                </article>
            </div>
        </section>

        <section id="advisory">
            <div class="content-wrapper">
                <h2>Strategic Advisory</h2>
                <p>Digital transformation and geopolitical positioning are no longer optional. We help you implement low-cost digital strategies and leverage European funding mechanisms (like Digital Europe and ESF+).</p>
                
                <div class="tool-wrapper">
                    <h3 style="margin-top: 0; font-size: 1.8rem;">SME Consulting Tool</h3>
                    <p style="font-family: sans-serif; color: #555;">Evaluate your current position. Answer the questions below to receive a customized, prioritized strategic action plan for your enterprise.</p>
                    
                    <label for="sme-size">1. Company Size</label>
                    <select id="sme-size">
                        <option value="micro">Micro (1-9 employees)</option>
                        <option value="small">Small (10-49 employees)</option>
                        <option value="medium">Medium (50-249 employees)</option>
                    </select>

                    <label for="sme-industry">2. Primary Industry</label>
                    <select id="sme-industry">
                        <option value="manufacturing">Manufacturing & Production</option>
                        <option value="tech">Technology & IT Services</option>
                        <option value="retail">Retail & E-Commerce</option>
                        <option value="services">Professional Services / Consulting</option>
                    </select>

                    <label for="sme-digi">3. Current Level of Digitalization</label>
                    <select id="sme-digi">
                        <option value="low">Low (Mostly paper/manual Excel)</option>
                        <option value="medium">Medium (Basic CRM/ERP in place)</option>
                        <option value="high">High (Automated workflows, data-driven)</option>
                    </select>

                    <button onclick="generateStrategy()">Generate Action Plan</button>

                    <div id="tool-result">
                        </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <div class="content-wrapper">
                <h2>Contact Us</h2>
                <p>Reach out for deep-dive strategy sessions or journalistic inquiries.</p>
                
                <form class="contact-form" name="contact" method="POST" data-netlify="true">
                    <label>Name</label>
                    <input type="text" name="name" required>
                    
                    <label>Email</label>
                    <input type="email" name="email" required>
                    
                    <label>Message</label>
                    <textarea name="message" rows="6" required></textarea>
                    
                    <button type="submit">Send Message</button>
                </form>
            </div>
        </section>

        <section id="impressum">
            <div class="content-wrapper">
                <h2>Impressum</h2>
                <p>Information corresponding to § 25 Mediengesetz (Austrian Media Law):</p>
                <p><strong>Media Owner and Publisher:</strong><br>
                [Your Name/Company Name]<br>
                [Your Address in Vienna]<br>
                Austria</p>
                <p><strong>Basic Direction of the Medium:</strong><br>
                LexdigestGlobal is an independent journalistic and advisory platform providing information on geopolitics, corporate strategy, and regulatory affairs.</p>
                <p><em>Note: Trade license (Gewerbe) registration pending successful Proof of Concept.</em></p>
            </div>
        </section>

    </main>

    <script>
        // Navigation Logic
        function showSection(sectionId) {
            const sections = document.querySelectorAll('section');
            sections.forEach(sec => sec.classList.remove('active'));
            document.getElementById(sectionId).classList.add('active');
            window.scrollTo(0, 0); // Scroll to top on navigation
        }

        // Logic for the SME Consulting Tool
        function generateStrategy() {
            const size = document.getElementById('sme-size').value;
            const industry = document.getElementById('sme-industry').value;
            const digi = document.getElementById('sme-digi').value;
            
            const resultDiv = document.getElementById('tool-result');
            let outputHTML = "<h3 style='margin-top: 0;'>Prioritized Strategic Recommendations</h3><ol style='font-family: serif; font-size: 1.1rem; padding-left: 20px;'>";

            if(digi === 'low') {
                outputHTML += "<li style='margin-bottom: 15px;'><strong>Priority 1 (Urgent): Digital Baseline.</strong> Establish core digital infrastructure immediately. Leverage EU funds (e.g., Digital Europe) to cover upskilling costs for your current staff. Delaying this threatens market survival within 24 months.</li>";
            } else if (digi === 'medium') {
                outputHTML += "<li style='margin-bottom: 15px;'><strong>Priority 1: Process Optimization.</strong> Your baseline is stable. Shift focus to interoperability between your tools and investigate AI-driven data analytics to identify hidden margin bleed.</li>";
            } else {
                outputHTML += "<li style='margin-bottom: 15px;'><strong>Priority 1: Tech-Led Scaling.</strong> You are digitally mature. Focus on using your tech stack to ensure compliance with incoming EU data regulations (like the AI Act) and use it as a competitive advantage.</li>";
            }

            if(industry === 'manufacturing' || industry === 'retail') {
                outputHTML += "<li style='margin-bottom: 15px;'><strong>Priority 2: Supply Chain Resilience.</strong> Current geopolitical volatility demands action. Implement a 'China + 1' or nearshoring strategy to secure raw materials and inventory within the European single market or allied zones.</li>";
            } else {
                outputHTML += "<li style='margin-bottom: 15px;'><strong>Priority 2: Talent & IP Retention.</strong> In the service/tech sector, your IP is your workforce. Develop aggressive retention strategies and utilize EU cross-border talent pools to mitigate local skill shortages.</li>";
            }

            if(size === 'micro') {
                outputHTML += "<li style='margin-bottom: 15px;'><strong>Priority 3: Lean Agility.</strong> As a micro-enterprise, avoid heavy consulting overhead. Utilize hybrid intelligence hubs (like LexdigestGlobal) and standardized SaaS tools to punch above your weight in operational efficiency.</li>";
            } else {
                outputHTML += "<li style='margin-bottom: 15px;'><strong>Priority 3: Structural Expansion.</strong> With your size, prepare for M&A opportunities. Distressed competitors failing to navigate regulatory complexity can become cheap acquisition targets for your expansion.</li>";
            }

            outputHTML += "</ol>";
            
            resultDiv.innerHTML = outputHTML;
            resultDiv.style.display = 'block';
        }
    </script>
</body>
</html>
