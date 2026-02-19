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


/* ===== DOKUMENTI - DROPDOWN GUMB ===== */

.docs-menu {
    position: fixed;
    top: 20px;
    right: 20px;
    z-index: 1000;
}

.docs-btn {
    background-color: #0078D4;
    color: white;
    padding: 10px 18px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-size: 16px;
}

.docs-dropdown {
    display: none;
    position: absolute;
    right: 0;
    background-color: #ffffff;
    min-width: 180px;
    border-radius: 6px;
    overflow: hidden;
    box-shadow: 0 8px 16px rgba(0,0,0,0.3);
}

.docs-dropdown a {
    display: block;
    padding: 12px 14px;
    color: #000;
    text-decoration: none;
}

.docs-dropdown a:hover {
    background: #f2f2f2;
}

.docs-show {
    display: block;
}


/* ===== LANGUAGE SELECTOR ===== */

.lang {
    margin-top: 25px;
    display: flex;
    justify-content: center;
    gap: 18px;
}

.lang-item {
    display: flex;
    flex-direction: column;
    align-items: center;
}

/* Gumbi zastav */
.lang button {
    width: 52px;
    height: 34px;
    border: 2px solid transparent;
    border-radius: 4px;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    cursor: pointer;
    padding: 0;
    transition: transform 0.1s ease, border 0.2s ease;
}

.lang button:hover {
    transform: translateY(-2px);
}

.lang button.active {
    border: 2px solid #ffffff;
    box-shadow: 0 0 6px rgba(255,255,255,0.8);
}

/* Kratice pod zastavami */
.lang-label {
    margin-top: 6px;
    font-size: 0.85rem;
    font-weight: bold;
    letter-spacing: 1px;
    color: #ffffff;
}

/* Zastave */
button[data-lang="si"] {
    background-image: url("https://flagcdn.com/w80/si.png");
}

button[data-lang="en"] {
    background-image: url("https://flagcdn.com/w80/gb.png");
}

button[data-lang="de"] {
    background-image: url("https://flagcdn.com/w80/de.png");
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

<div class="docs-menu">
    <button id="docsBtn" class="docs-btn" onclick="toggleDocs()" aria-haspopup="true" aria-expanded="false">Dokumenti ▾</button>
    <div id="docsDropdown" class="docs-dropdown" role="menu" aria-labelledby="docsBtn">
        <!-- Linke polnimo dinamično glede na jezik -->
    </div>
</div>

<header>
    <h1 id="title"></h1>
    <h2>Marjan Pleger s.p.</h2>

    <div class="lang">
        <div class="lang-item">
            <button onclick="setLang('si')" data-lang="si" aria-label="Slovenščina"></button>
            <div class="lang-label">SI</div>
        </div>

        <div class="lang-item">
            <button onclick="setLang('en')" data-lang="en" aria-label="English"></button>
            <div class="lang-label">AN</div>
        </div>

        <div class="lang-item">
            <button onclick="setLang('de')" data-lang="de" aria-label="Deutsch"></button>
            <div class="lang-label">DE</div>
        </div>
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
function toggleDocs() {
    const dd = document.getElementById("docsDropdown");
    const btn = document.getElementById("docsBtn");
    const willShow = !dd.classList.contains("docs-show");
    dd.classList.toggle("docs-show");
    btn.setAttribute("aria-expanded", willShow ? "true" : "false");
}

// Zapiranje dropdowna, ko klikneš izven njega
window.addEventListener("click", function(event) {
    const btn = document.getElementById("docsBtn");
    const dd  = document.getElementById("docsDropdown");
    const clickedBtn = event.target === btn;
    const clickedInsideDropdown = dd.contains(event.target);
    if (!clickedBtn && !clickedInsideDropdown && dd.classList.contains("docs-show")) {
        dd.classList.remove("docs-show");
        btn.setAttribute("aria-expanded", "false");
    }
});

const content = {
    si: {
        title: "INŽENIRING NA PODROČJU PLASTIKE",
        docsTitle: "Dokumenti",
        documents: ["Dokument 1", "Dokument 2", "Dokument 3"],
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
        docsTitle: "Documents",
        documents: ["Document 1", "Document 2", "Document 3"],
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
        docsTitle: "Dokumente",
        documents: ["Dokument 1", "Dokument 2", "Dokument 3"],
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

    // jezik dokumenta (npr. za bralnike in SEO)
    document.documentElement.lang = lang;

    // Naslovi, besedila
    document.getElementById("title").innerText = data.title;
    document.getElementById("aboutTitle").innerText = data.aboutTitle;
    document.getElementById("aboutText").innerText = data.aboutText;
    document.getElementById("servicesTitle").innerText = data.servicesTitle;
    document.getElementById("contactTitle").innerText = data.contactTitle;
    document.getElementById("contactText").innerHTML = data.contactText;
    document.getElementById("footer").innerText = data.footer;

    // Storitve (seznam)
    const list = document.getElementById("servicesList");
    list.innerHTML = "";
    data.services.forEach(item => {
        const li = document.createElement("li");
        li.innerText = item;
        list.appendChild(li);
    });

    // *** DOKUMENTI: posodobi gumb in dropdown ***
    const docsBtn = document.getElementById("docsBtn");
    const docsDropdown = document.getElementById("docsDropdown");

    docsBtn.innerText = data.docsTitle + " ▾";
    docsBtn.setAttribute("aria-label", data.docsTitle);

    // Po želji: prevedi tudi imena dokumentov
    const docLinks = [
        { href: "dokument1.pdf" },
        { href: "dokument2.pdf" },
        { href: "dokument3.pdf" }
    ];
    docsDropdown.innerHTML = "";
    data.documents.forEach((label, idx) => {
        const a = document.createElement("a");
        a.href = docLinks[idx]?.href || "#";
        a.target = "_blank";
        a.innerText = label;
        a.setAttribute("role", "menuitem");
        docsDropdown.appendChild(a);
    });

    // Aktivni indikator na zastavi
    document.querySelectorAll(".lang button").forEach(btn => {
        btn.classList.toggle("active", btn.dataset.lang === lang);
    });

    // Ob menjavi jezika zapri odprt dropdown
    if (docsDropdown.classList.contains("docs-show")) {
        docsDropdown.classList.remove("docs-show");
        docsBtn.setAttribute("aria-expanded", "false");
    }

    // Shrani izbiro
    localStorage.setItem("lang", lang);
}

const savedLang = localStorage.getItem("lang") || "si";
setLang(savedLang);
</script>

</body>
</html>
