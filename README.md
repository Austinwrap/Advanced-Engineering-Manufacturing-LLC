<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Advanced Engineering & Manufacturing LLC</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            color: #e0e0e0;
            line-height: 1.6;
            overflow-x: hidden;
        }

        #welcome {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100vh;
            background: linear-gradient(135deg, rgba(0, 0, 0, 0.9), rgba(26, 26, 46, 0.8));
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            z-index: 2000;
            overflow: hidden;
        }

        #welcome.hidden {
            display: none;
        }

        #welcome h1 {
            font-size: 8vw;
            font-weight: 700;
            color: #00ddeb;
            text-shadow: 0 0 20px rgba(0, 221, 235, 0.8), 0 0 40px rgba(0, 221, 235, 0.4);
            animation: glow 2s infinite alternate;
            margin-bottom: 2vh;
        }

        @keyframes glow {
            0% { text-shadow: 0 0 20px rgba(0, 221, 235, 0.8), 0 0 40px rgba(0, 221, 235, 0.4); }
            100% { text-shadow: 0 0 30px rgba(0, 221, 235, 1), 0 0 60px rgba(0, 221, 235, 0.6); }
        }

        #welcome p {
            font-size: 3.5vw;
            max-width: 80%;
            color: #b0b0b0;
            margin-bottom: 4vh;
        }

        #welcome button {
            background: linear-gradient(45deg, #00ddeb, #0077cc);
            border: none;
            padding: 2vh 5vw;
            font-size: 3.5vw;
            color: white;
            cursor: pointer;
            border-radius: 25px;
            box-shadow: 0 0 15px rgba(0, 221, 235, 0.5);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        #welcome button:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 25px rgba(0, 221, 235, 0.8);
        }

        header {
            background: rgba(0, 0, 0, 0.9);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 1vh 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
            display: none;
        }

        header.visible {
            display: block;
        }

        header nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 4vw;
        }

        header h1 {
            font-size: 4vw;
            font-weight: 600;
            color: #00ddeb;
        }

        header .nav-links a {
            color: #e0e0e0;
            text-decoration: none;
            margin-left: 3vw;
            font-weight: 400;
            font-size: 3vw;
            transition: color 0.3s;
            cursor: pointer;
        }

        header .nav-links a:hover {
            color: #00ddeb;
        }

        #main-content, #get-started {
            display: none;
        }

        #main-content.visible, #get-started.visible {
            display: block;
        }

        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7));
            padding: 0 4vw;
        }

        .hero h2 {
            font-size: 6vw;
            font-weight: 700;
            color: #fff;
            margin-bottom: 2vh;
        }

        .hero p {
            font-size: 3.5vw;
            max-width: 80%;
            color: #b0b0b0;
            margin-bottom: 4vh;
        }

        .hero button, #get-started button {
            background: linear-gradient(45deg, #00ddeb, #0077cc);
            border: none;
            padding: 2vh 5vw;
            font-size: 3.5vw;
            color: white;
            cursor: pointer;
            border-radius: 25px;
            box-shadow: 0 0 15px rgba(0, 221, 235, 0.5);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .hero button:hover, #get-started button:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 25px rgba(0, 221, 235, 0.8);
        }

        section {
            padding: 8vh 4vw;
            max-width: 1200px;
            margin: 0 auto;
        }

        h2 {
            font-size: 5vw;
            font-weight: 600;
            color: #00ddeb;
            text-align: center;
            margin-bottom: 4vh;
        }

        #about p {
            max-width: 80%;
            margin: 0 auto;
            font-size: 3vw;
            color: #b0b0b0;
            text-align: center;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(45vw, 1fr));
            gap: 4vw;
            margin: 4vh 0;
        }

        .service-item {
            background: #16213e;
            padding: 3vh;
            border-radius: 10px;
            text-align: center;
            transition: transform 0.3s, box-shadow 0.3s;
            border: 1px solid transparent;
            box-shadow: 0 0 10px rgba(0, 221, 235, 0.3), inset 0 0 5px rgba(0, 221, 235, 0.2);
        }

        .service-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 20px rgba(0, 221, 235, 0.6), inset 0 0 10px rgba(0, 221, 235, 0.4);
        }

        .service-item h3 {
            color: #00ddeb;
            font-size: 3.5vw;
            margin-bottom: 1vh;
        }

        .service-item p {
            color: #b0b0b0;
            font-size: 2.5vw;
        }

        #get-started form {
            display: flex;
            flex-direction: column;
            gap: 3vh;
            max-width: 90%;
            margin: 4vh auto;
            background: #16213e;
            padding: 4vh;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 221, 235, 0.3);
        }

        #get-started label {
            font-weight: 600;
            color: #00ddeb;
            font-size: 3vw;
        }

        #get-started input, #get-started textarea {
            padding: 2vh;
            border: none;
            border-radius: 5px;
            background: #0f1626;
            color: #e0e0e0;
            font-size: 3vw;
            transition: box-shadow 0.3s;
        }

        #get-started input:focus, #get-started textarea:focus {
            outline: none;
            box-shadow: 0 0 10px rgba(0, 221, 235, 0.5);
        }

        #get-started textarea {
            resize: vertical;
            min-height: 20vh;
        }

        footer {
            text-align: center;
            padding: 4vh;
            background: rgba(0, 0, 0, 0.9);
            color: #b0b0b0;
            font-size: 2.5vw;
        }

        footer a {
            color: #00ddeb;
            text-decoration: none;
            transition: color 0.3s;
        }

        footer a:hover {
            color: #0077cc;
        }

        @media (max-width: 414px) {
            #welcome h1 { font-size: 10vw; }
            #welcome p, .hero p { font-size: 4.5vw; }
            #welcome button, .hero button, #get-started button { font-size: 4.5vw; padding: 2vh 6vw; }
            header h1 { font-size: 5vw; }
            header .nav-links a { font-size: 3.5vw; margin-left: 2vw; }
            .hero h2 { font-size: 8vw; }
            h2 { font-size: 6vw; }
            #about p { font-size: 3.5vw; }
            .service-item h3 { font-size: 4.5vw; }
            .service-item p { font-size: 3vw; }
            #get-started label { font-size: 4vw; }
            #get-started input, #get-started textarea { font-size: 3.5vw; }
            footer { font-size: 3vw; }
        }
    </style>
</head>
<body>
    <div id="welcome">
        <h1>Advanced Engineering & Manufacturing LLC</h1>
        <p>Precision Innovation in Bristol, CT—Transforming Your Ideas into Reality</p>
        <button onclick="enterSite()">Enter Site</button>
    </div>

    <header>
        <nav>
            <h1>Advanced Engineering & Manufacturing LLC</h1>
            <div class="nav-links">
                <a onclick="scrollToSection('home')">Home</a>
                <a onclick="scrollToSection('about')">About</a>
                <a onclick="scrollToSection('services')">Services</a>
                <a onclick="showGetStarted()">Get Started</a>
            </div>
        </nav>
    </header>

    <div id="main-content">
        <section id="home" class="hero">
            <h2>Innovate. Design. Create.</h2>
            <p>Advanced Engineering & Manufacturing LLC transforms your ideas into reality with cutting-edge technology in Bristol, CT.</p>
            <button onclick="showGetStarted()">Get Started</button>
        </section>

        <section id="about">
            <h2>About Us</h2>
            <p>Founded by Adam Cote in Bristol, CT, Advanced Engineering & Manufacturing LLC is your partner in precision innovation. With a state-of-the-art workshop featuring CNC machines, lasers, and SLA/FDM 3D printers, Adam brings expertise in CNC machining, R&D, prototyping, 3D modeling with SolidWorks, product design, and CNC programming. Specializing in design for manufacturability and lean manufacturing consulting, we deliver custom solutions that turn your ideas into reality with efficiency and creativity.</p>
        </section>

        <section id="services">
            <h2>Our Capabilities</h2>
            <div class="service-grid">
                <div class="service-item">
                    <h3>CNC Machining</h3>
                    <p>High-precision machining for custom parts and prototypes.</p>
                </div>
                <div class="service-item">
                    <h3>R&D</h3>
                    <p>Research and development to innovate and refine your concepts.</p>
                </div>
                <div class="service-item">
                    <h3>Prototyping</h3>
                    <p>Rapid prototyping to test and perfect your designs.</p>
                </div>
                <div class="service-item">
                    <h3>SLA 3D Printing</h3>
                    <p>High-resolution 3D printing for detailed, smooth finishes.</p>
                </div>
                <div class="service-item">
                    <h3>FDM 3D Printing</h3>
                    <p>Versatile 3D printing for functional parts and models.</p>
                </div>
                <div class="service-item">
                    <h3>Laser Cutting</h3>
                    <p>Accurate cutting for a wide range of materials.</p>
                </div>
                <div class="service-item">
                    <h3>Engraving</h3>
                    <p>Custom engravings for branding or personalization.</p>
                </div>
                <div class="service-item">
                    <h3>3D Modeling with SolidWorks</h3>
                    <p>Expert 3D modeling for precise design visualization.</p>
                </div>
                <div class="service-item">
                    <h3>Product Design</h3>
                    <p>End-to-end design services for market-ready products.</p>
                </div>
                <div class="service-item">
                    <h3>CNC Programming</h3>
                    <p>Custom programming for optimized machining processes.</p>
                </div>
                <div class="service-item">
                    <h3>Design for Manufacturability</h3>
                    <p>Optimizing designs for efficient production.</p>
                </div>
                <div class="service-item">
                    <h3>Lean Manufacturing Consulting</h3>
                    <p>Streamlining operations for maximum efficiency.</p>
                </div>
            </div>
        </section>

        <footer>
            <p>© 2025 Advanced Engineering & Manufacturing LLC | Bristol, CT | Email: <a href="mailto:Acote@advancedengllc.com">Acote@advancedengllc.com</a></p>
        </footer>
    </div>

    <div id="get-started">
        <section>
            <h2>Share Your Vision</h2>
            <form id="contact-form">
                <label for="name">Your Name:</label>
                <input type="text" id="name" name="name" required>
                
                <label for="email">Your Email:</label>
                <input type="email" id="email" name="email" required>
                
                <label for="idea">Your Project Idea:</label>
                <textarea id="idea" name="idea" rows="5" required placeholder="Tell us about your idea!"></textarea>
                
                <button type="submit">Submit Idea</button>
            </form>
        </section>
        <footer>
            <p>© 2025 Advanced Engineering & Manufacturing LLC | Bristol, CT | Email: <a href="mailto:Acote@advancedengllc.com">Acote@advancedengllc.com</a></p>
        </footer>
    </div>

    <script>
        function enterSite() {
            document.getElementById('welcome').classList.add('hidden');
            document.querySelector('header').classList.add('visible');
            document.getElementById('main-content').classList.add('visible');
            document.body.style.overflow = 'auto'; // Enable scrolling after entering
        }

        function showGetStarted() {
            document.getElementById('main-content').classList.remove('visible');
            document.getElementById('get-started').classList.add('visible');
            window.scrollTo(0, 0); // Reset scroll position
        }

        function scrollToSection(sectionId) {
            document.getElementById('get-started').classList.remove('visible');
            document.getElementById('main-content').classList.add('visible');
            document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
        }

        document.getElementById('contact-form').addEventListener('submit', function(e) {
            e.preventDefault();
            
            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const idea = document.getElementById('idea').value;
            
            const subject = encodeURIComponent(`New Project Idea from ${name}`);
            const body = encodeURIComponent(
                `Hi Adam,\n\n` +
                `Name: ${name}\n` +
                `Email: ${email}\n` +
                `Project Idea:\n${idea}\n\n` +
                `Looking forward to hearing from you!\n` +
                `Best,\n${name}`
            );
            
            const mailtoLink = `mailto:Acote@advancedengllc.com?subject=${subject}&body=${body}`;
            window.location.href = mailtoLink;
            
            this.reset();
        });
    </script>
</body>
</html>
