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
    display: flex;
    align-items: center;
    gap: 6px;
}

.docs-btn-arrow {
    margin-left: 4px;
    font-size: 14px;
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

<!-- POPRAVLJEN GUMB -->
<div class="docs-menu">
    <button id="docsBtn" class="docs-btn" onclick="toggleDocs()">
        <span id="docsLabel">Dokumenti</span>
        <span class="docs-btn-arrow">▾</span>
    </button>

    <div id="docsDropdown" class="docs-dropdown"></div>
</div>

<header>
    <h1 id="title"></h1>
    <h2>Marjan Pleger s.p.</h2>

    <div class="lang">
        <div class="lang-item">
            <button onclick="setLang('si')" data-lang="si"></button>
            <div class="lang-label">SI</div>
        </div>

        <div class="lang-item">
            <button onclick="setLang('en')" data-lang="en"></button>
            <div class="lang-label">AN</div>
        </div>

        <div class="lang-item">
            <button onclick="setLang('de')" data-lang="de"></button>
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
    dd.classList.toggle("docs-show");
}

// zapiranje dropdowna
window.addEventListener("click", function(event) {
    const btn = document.getElementById("docsBtn");
    const dd  = document.getElementById("docsDropdown");
    if (!btn.contains(event.target) && !dd.contains(event.target)) {
        dd.classList.remove("docs-show");
    }
});

const content = {
    si: { docsTitle: "Dokumenti", documents: ["Dokument 1","Dokument 2","Dokument 3"],
          title:"INŽENIRING NA PODROČJU PLASTIKE", aboutTitle:"O podjetju",
          aboutText:"Več kot 20 let izkušenj ...",
          servicesTitle:"Storitve", services:["Konstruiranje...", "Moldflow analiza"],
          contactTitle:"Kontakt", contactText:"📍 Slovenija<br>📧 ...", footer:"© 2026 ..." },

    en: { docsTitle: "Documents", documents: ["Document 1","Document 2","Document 3"],
          title:"PLASTIC ENGINEERING", aboutTitle:"About Us",
          aboutText:"Over 20 years ...",
          servicesTitle:"Services", services:["Injection mold design","Rubber mold design"],
          contactTitle:"Contact", contactText:"📍 Slovenia<br>📧 ...", footer:"© 2026 ..." },

    de: { docsTitle: "Dokumente", documents: ["Dokument 1","Dokument 2","Dokument 3"],
          title:"KUNSTSTOFFTECHNIK", aboutTitle:"Über uns",
          aboutText:"Über 20 Jahre ...",
          servicesTitle:"Dienstleistungen", services:["Spritzguss...","DFM erstellen"],
          contactTitle:"Kontakt", contactText:"📍 Slowenien<br>📧 ...", footer:"© 2026 ..." }
};

function setLang(lang) {
    const d = content[lang];

    document.getElementById("docsLabel").innerText = d.docsTitle;

    const dropdown = document.getElementById("docsDropdown");
    dropdown.innerHTML = "";
    d.documents.forEach(name => {
        const a = document.createElement("a");
        a.innerText = name;
        a.href = "#";
        dropdown.appendChild(a);
    });

    document.getElementById("title").innerText = d.title;
    document.getElementById("aboutTitle").innerText = d.aboutTitle;
    document.getElementById("aboutText").innerText = d.aboutText;
    document.getElementById("servicesTitle").innerText = d.servicesTitle;
    document.getElementById("contactTitle").innerText = d.contactTitle;
    document.getElementById("contactText").innerHTML = d.contactText;
    document.getElementById("footer").innerText = d.footer;

    const list = document.getElementById("servicesList");
    list.innerHTML = "";
    d.services.forEach(s => {
        const li = document.createElement("li");
        li.innerText = s;
        list.appendChild(li);
    });

    document.querySelectorAll(".lang button").forEach(btn =>
        btn.classList.toggle("active", btn.dataset.lang === lang)
    );

    localStorage.setItem("lang", lang);
}

setLang(localStorage.getItem("lang") || "si");
</script>

</body>
</html>
``
