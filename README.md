<html lang="sl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Plastic Engineering | Marjan Pleger s.p.</title>

    <style>
        body {
            margin: 0;
            font-family: Arial, Helvetica, sans-serif;
            color: white;
            background:
                linear-gradient(rgba(0,40,90,0.85), rgba(0,40,90,0.85)),
                url("https://images.unsplash.com/photo-1581091012184-5c7b8b6c9b5c");
            background-size: cover;
            background-position: center;
        }

        header {
            text-align: center;
            padding: 120px 20px 80px;
        }

        header h1 {
            font-size: 3rem;
            margin-bottom: 10px;
        }

        header h2 {
            font-weight: normal;
            font-size: 1.4rem;
            opacity: 0.9;
        }

        .lang {
            margin-top: 20px;
        }

        .lang button {
            background: rgba(255,255,255,0.15);
            border: none;
            color: white;
            padding: 8px 14px;
            margin: 0 5px;
            cursor: pointer;
            border-radius: 5px;
        }

        .lang button:hover {
            background: rgba(255,255,255,0.3);
        }

        section {
            max-width: 1000px;
            margin: auto;
            padding: 60px 20px;
        }

        .box {
            background: rgba(255,255,255,0.08);
            padding: 30px;
            border-radius: 10px;
            margin-bottom: 30px;
        }

        h3 {
            color: #9ecbff;
        }

        footer {
            text-align: center;
            padding: 30px;
            font-size: 0.9rem;
            background: rgba(0,0,0,0.3);
        }
    </style>
</head>
<body>

<header>
    <h1 id="title">INŽENIRING NA PODROČJU PLASTIKE</h1>
    <h2 id="subtitle">Marjan Pleger s.p.</h2>

    <div class="lang">
        <button onclick="setLang('si')">SL</button>
        <button onclick="setLang('en')">EN</button>
        <button onclick="setLang('de')">DE</button>
    </div>
</header>

<section>
    <div class="box">
        <h3 id="aboutTitle">O podjetju</h3>
        <p id="aboutText">
            Več kot 20 let izkušenj s področja strokovnih inženirskih rešitev
            na področju plastike in gume – od ideje do izvedbe.
        </p>
    </div>

    <div class="box">
        <h3 id="servicesTitle">Storitve</h3>
        <ul id="servicesList">
            <li>Konstruiranje orodij za brizganje plastike</li>
            <li>Konstruiranje orodij za brizganje gume ali stiskanje gume</li>
            <li>Konstruiranje plastičnih izdelkov</li>
            <li>Konstruiranje gumjastih izdelkov</li>
            <li>Inženirsko svetovanje na področju plastike in gume</li>
            <li>Razvoj in optimizacija plastičnih in gumenih izdelkov</li>
            <li>Tehnična dokumentacija</li>
            <li>Podpora pri proizvodnji</li>
        </ul>
    </div>

    <div class="box">
        <h3 id="contactTitle">Kontakt</h3>
        <p id="contactText">
            📍 Slovenija<br>
            📧 E-pošta: (plegerm@gmail.com)<br>
            📞 Telefon: (+386 41 804 143)
        </p>
    </div>
</section>

<footer id="footerText">
    © 2026 Marjan Pleger s.p. | Inženiring na področju plastike
</footer>

<script>
const content = {
    si: {
        title: "INŽENIRING NA PODROČJU PLASTIKE",
        aboutTitle: "O podjetju",
        aboutText: "Podjetje Marjan Pleger s.p. nudi strokovne inženirske rešitve na področju plastike – od ideje do izvedbe.",
        servicesTitle: "Storitve",
        services: [
            "Inženirsko svetovanje",
            "Razvoj plastičnih izdelkov",
            "Tehnična dokumentacija",
            "Podpora pri proizvodnji"
        ],
        contactTitle: "Kontakt",
        footer: "© 2026 Marjan Pleger s.p. | Inženiring na področju plastike"
    },
    en: {
        title: "PLASTIC ENGINEERING",
        aboutTitle: "About Us",
        aboutText: "Marjan Pleger s.p. provides professional engineering solutions in the field of plastics – from concept to production
