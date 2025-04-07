<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Advanced Engineering LLC</title>
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

        header {
            background: rgba(0, 0, 0, 0.9);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.3);
        }

        header nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        header h1 {
            font-size: 1.8rem;
            font-weight: 600;
            color: #00ddeb;
        }

        header .nav-links a {
            color: #e0e0e0;
            text-decoration: none;
            margin-left: 1.5rem;
            font-weight: 400;
            transition: color 0.3s;
            cursor: pointer;
        }

        header .nav-links a:hover {
            color: #00ddeb;
        }

        .hero {
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7));
            padding: 0 2rem;
        }

        .hero h1 {
            font-size: 4.5rem;
            font-weight: 700;
            color: #00ddeb;
            text-shadow: 0 0 20px rgba(0, 221, 235, 0.8), 0 0 40px rgba(0, 221, 235, 0.4);
            animation: glow 2s infinite alternate;
            margin-bottom: 1rem;
        }

        @keyframes glow {
            0% { text-shadow: 0 0 20px rgba(0, 221, 235, 0.8), 0 0 40px rgba(0, 221, 235, 0.4); }
            100% { text-shadow: 0 0 30px rgba(0, 221, 235, 1), 0 0 60px rgba(0, 221, 235, 0.6); }
        }

        .hero p {
            font-size: 1.5rem;
            max-width: 600px;
            color: #b0b0b0;
            margin-bottom: 2rem;
        }

        .hero button {
            background: linear-gradient(45deg, #00ddeb, #0077cc);
            border: none;
            padding: 1rem 2.5rem;
            font-size: 1.2rem;
            color: white;
            cursor: pointer;
            border-radius: 25px;
            box-shadow: 0 0 15px rgba(0, 221, 235, 0.5);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        .hero button:hover {
            transform: translateY(-5px);
            box-shadow: 0 0 25px rgba(0, 221, 235, 0.8);
        }

        section {
            padding: 4rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        h2 {
            font-size: 2.5rem;
            font-weight: 600;
            color: #00ddeb;
            text-align: center;
            margin-bottom: 2rem;
        }

        #about p {
            max-width: 800px;
            margin: 0 auto;
            font-size: 1.1rem;
            color: #b0b0b0;
            text-align: center;
        }

        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 2rem 0;
        }

        .service-item {
            background: #16213e;
            padding: 1.5rem;
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
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
        }

        .service-item p {
            color: #b0b0b0;
            font-size: 1rem;
        }

        #contact form {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            max-width: 600px;
            margin: 2rem auto;
            background: #16213e;
            padding: 2rem;
            border-radius: 10px;
            box-shadow: 0 0 15px rgba(0, 221, 235, 0.3);
        }

        #contact label {
            font-weight: 600;
            color: #00ddeb;
        }

        #contact input, #contact textarea {
            padding: 0.8rem;
            border: none;
            border-radius: 5px;
            background: #0f1626;
            color: #e0e0e0;
            font-size: 1rem;
            transition: box-shadow 0.3s;
        }

        #contact input:focus, #contact textarea:focus {
            outline: none;
            box-shadow: 0 0 10px rgba(0, 221, 235, 0.5);
        }

        #contact textarea {
            resize: vertical;
        }

        #contact button {
            background: linear-gradient(45deg, #00ddeb, #0077cc);
            border: none;
            padding: 0.8rem;
            font-size: 1.1rem;
            color: white;
            cursor: pointer;
            border-radius: 25px;
            box-shadow: 0 0 15px rgba(0, 221, 235, 0.5);
            transition: transform 0.3s, box-shadow 0.3s;
        }

        #contact button:hover {
            transform: translateY(-3px);
            box-shadow: 0 0 25px rgba(0, 221, 235, 0.8);
        }

        footer {
            text-align: center;
            padding: 2rem;
            background: rgba(0, 0, 0, 0.9);
            color: #b0b0b0;
        }

        footer a {
            color: #00ddeb;
            text-decoration: none;
            transition: color 0.3s;
        }

        footer a:hover {
            color: #0077cc;
        }

        @media (max-width: 768px) {
            .hero h1 { font-size: 3rem; }
            .hero p { font-size: 1.2rem; }
            header h1 { font-size: 1.5rem; }
            header .nav-links a { margin-left: 1rem; font-size: 0.9rem; }
            h2 { font-size: 2rem; }
        }
    </style>
</head>
<body>
    <header>
        <nav>
            <h1>Advanced Engineering LLC</h1>
            <div class="nav-links">
                <a onclick="scrollToSection('home')">Home</a>
                <a onclick="scrollToSection('about')">About</a>
                <a onclick="scrollToSection('services')">Services</a>
                <a onclick="scrollToSection('contact')">Contact</a>
            </div>
        </nav>
    </header>

    <section id="home" class="hero">
        <h1>Advanced Engineering LLC</h1>
        <p>Precision Innovation in Bristol, CT—Transforming Your Ideas into Reality</p>
        <button onclick="scrollToSection('contact')">Get Started</button>
    </section>

    <section id="about">
        <h2>About Us</h2>
        <p>Founded by Adam Cote in Bristol, CT, Advanced Engineering LLC is your partner in precision innovation. With a state-of-the-art workshop featuring CNC machines, lasers, and SLA/FDM 3D printers, Adam brings expertise in CNC machining, R&D, prototyping, 3D modeling with SolidWorks, product design, and CNC programming. Specializing in design for manufacturability and lean manufacturing consulting, we deliver custom solutions that turn your ideas into reality with efficiency and creativity.</p>
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

    <section id="contact">
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
        <p>© 2025 Advanced Engineering LLC | Bristol, CT | Email: <a href="mailto:Acote@advancedengllc.com">Acote@advancedengllc.com</a></p>
    </footer>

    <script>
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

        function scrollToSection(sectionId) {
            document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
        }
    </script>
</body>
</html>
