<html lang="sl">
<head>
<meta charset="UTF-8">
<title>Plastic Engineering | Marjan Pleger s.p.</title>

<style>
body {
    margin: 0;
    font-family: Arial, Helvetica, sans-serif;
    color: white;
    background-color: #0a1a2f;
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

/* ===== LANGUAGE BUTTONS ===== */

.lang {
    margin-top: 25px;
}

.lang button {
    width: 46px;
    height: 32px;
    margin: 0 6px;
    border: 2px solid transparent;
    border-radius: 4px;
    background-size: cover;
    background-position: center;
    cursor: pointer;
    transition: transform 0.1s ease, border 0.2s ease;
}

.lang button:hover {
    transform: translateY(-2px);
}

.lang button.active {
    border: 2px solid #ffffff;
    box-shadow: 0 0 6px rgba(255,255,255,0.8);
}

/* Zastave */
.lang button[data-lang="si"] {
    background-image: url("https://flagcdn.com/w40/si.png");
}

.lang button[data-lang="en"] {
    background-image: url("https://flagcdn.com/w40/gb.png");
}

.lang button[data-lang="de"] {
    background-image: url("https://flagcdn.com/w40/de.png");
}

/* ============================ */

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
    <h1 id="title"></h1>
    <h2>Marjan Pleger s.p.</h2>

    <div class="lang">
        <button onclick="setLang('si')" data-lang="si" aria-label="Slovenščina"></button>
        <button onclick="setLang('en')" data-lang="en" aria-label="English"></button>
        <button onclick="setLang('de')" data-lang="de" aria-label="Deutsch"></button>
    </div>
</header>

<section>
    <div class="box">
        <h3 id="aboutTitle"></h3>
        <p id="aboutText"></p>
    </div>

    <div class="box">
        <h3 id="servicesTitle"></h3>
        <ul id="servicesList"></ul>
    </div>

    <div class="box">
        <h3 id="contactTitle"></h3>
        <p id="contactText"></p>
    </div>
</section>

<footer id="footer"></footer>

<script>
const content = {
    si: {
        title: "INŽENIRING NA PODROČJU PLASTIKE",
        aboutTitle: "O podjetju",
        aboutText: "Več kot 20 let izkušenj s področja strokovnih inženirskih rešitev na področju plastike in gume – od ideje do izvedbe.",
        servicesTitle: "Storitve",
        services: [
            "Konstruiranje orodij za brizganje plastike",
            "Konstruiranje orodij za brizganje ali stiskanje gume",
            "Konstruiranje plastičnih izdelkov",
            "Konstruiranje gumjastih izdelkov",
            "Moldflow analiza",
            "Izdelava DFM",
            "Inženirsko svetovanje",
            "Razvoj in optimizacija izdelkov",
            "Tehnična dokumentacija",
            "Podpora pri proizvodnji"
        ],
        contactTitle: "Kontakt",
        contactText: "📍 Slovenija<br>📧 E-pošta: plegerm@gmail.com<br>📞 Telefon: +386 41 804 143",
        footer: "© 2026 Marjan Pleger s.p. | Inženiring na področju plastike"
    },

    en: {
        title: "PLASTIC ENGINEERING",
        aboutTitle: "About Us",
        aboutText: "Over 20 years of experience providing professional engineering solutions in plastics and rubber – from concept to production.",
        servicesTitle: "Services",
        services: [
            "Injection mold design",
            "Rubber mold design",
            "Plastic product design",
            "Rubber product design",
            "Moldflow analysis",
            "Preparing DFM",
            "Engineering consulting",
            "Product development and optimization",
            "Technical documentation",
            "Production support"
        ],
        contactTitle: "Contact",
        contactText: "📍 Slovenia<br>📧 Email: plegerm@gmail.com<br>📞 Phone: +386 41 804 143",
        footer: "© 2026 Marjan Pleger s.p. | Plastic Engineering"
    },

    de: {
        title: "KUNSTSTOFFTECHNIK",
        aboutTitle: "Über uns",
        aboutText: "Über 20 Jahre Erfahrung in professionellen Ingenieurlösungen im Bereich Kunststoff und Gummi – von der Idee bis zur Umsetzung.",
        servicesTitle: "Dienstleistungen",
        services: [
            "Spritzgusswerkzeug-Konstruktion",
            "Gummiwerkzeug-Konstruktion",
            "Kunststoffproduktentwicklung",
            "Gummiproduktentwicklung",
            "Moldflow Analyse",
            "Erstellen DFM",
            "Ingenieurberatung",
            "Produktentwicklung und Optimierung",
            "Technische Dokumentation",
            "Produktionsunterstützung"
        ],
        contactTitle: "Kontakt",
        contactText: "📍 Slowenien<br>📧 E-Mail: plegerm@gmail.com<br>📞 Telefon: +386 41 804 143",
        footer: "© 2026 Marjan Pleger s.p. | Kunststofftechnik"
    }
};

function setLang(lang) {
    const data = content[lang];

    document.documentElement.lang = lang;
    document.getElementById("title").innerText = data.title;
    document.getElementById("aboutTitle").innerText = data.aboutTitle;
    document.getElementById("aboutText").innerText = data.aboutText;
    document.getElementById("servicesTitle").innerText = data.servicesTitle;
    document.getElementById("contactTitle").innerText = data.contactTitle;
    document.getElementById("contactText").innerHTML = data.contactText;
    document.getElementById("footer").innerText = data.footer;

    const list = document.getElementById("servicesList");
    list.innerHTML = "";
    data.services.forEach(item => {
        const li = document.createElement("li");
        li.innerText = item;
        list.appendChild(li);
    });

    document.querySelectorAll(".lang button").forEach(btn => {
        btn.classList.toggle("active", btn.dataset.lang === lang);
    });

    localStorage.setItem("lang", lang);
}

const savedLang = localStorage.getItem("lang") || "si";
setLang(savedLang);
</script>

</body>
</html>
