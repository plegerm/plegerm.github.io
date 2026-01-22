<!DOCTYPE html>
<html lang="sl">
<head>
<meta charset="UTF-8">
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
    margin-top: 25px;
}

.lang button {
    background: rgba(255,255,255,0.15);
    border: none;
    color: white;
    padding: 8px 14px;
    margin: 0 5px;
    cursor: pointer;
    border-radius: 6px;
    display: inline-flex;
    align-items: center;
    gap: 6px;
    transition: background 0.2s ease, transform 0.1s ease;
}

.lang button:hover {
    background: rgba(255,255,255,0.3);
    transform: translateY(-1px);
}

.lang button.active {
    background: rgba(255,255,255,0.5);
    color: #003366;
    font-weight: bold;
    box-shadow: 0 0 0 2px rgba(255,255,255,0.6) inset;
}

.lang button span {
    font-size: 0.8rem;
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
    <h1 id="title"></h1>
    <h2>Marjan Pleger s.p.</h2>

    <div class="lang">
        <button onclick="setLang('si')" data-lang="si">🇸🇮 <span>SL</span></button>
        <button onclick="setLang('en')" data-lang="en">🇬🇧 <span>EN</span></button>
        <button onclick="setLang('de')" data-lang="de">🇩🇪 <span>DE</span></button>
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
