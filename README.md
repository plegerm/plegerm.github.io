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
    si: { 
        docsTitle: "Dokumenti",
        documents: [
            {
                name: "Zahteve za izdelavo konstrukcije",
                url: "https://raw.githubusercontent.com/plegerm/plegerm.github.io/main/Zahteve%20za%20izdelavo%20konstrukcije.docx"
            }
        ],
        title:"INŽENIRING NA PODROČJU PLASTIKE",
        aboutTitle:"O podjetju",
        aboutText:"Več kot 20 let izkušenj ...",
        servicesTitle:"Storitve",
        services:["Konstruiranje...", "Moldflow analiza"],
        contactTitle:"Kontakt",
        contactText:"📍 Slovenija<br>📧 ...",
        footer:"© 2026 ..."
    },

    en: { 
        docsTitle: "Documents",
        documents: [
            {
                name: "Requirements for tool design",
                url: "https://raw.githubusercontent.com/plegerm/plegerm.github.io/main/Zahteve%20za%20izdelavo%20konstrukcije.docx"
            }
        ],
        title:"PLASTIC ENGINEERING",
        aboutTitle:"About Us",
        aboutText:"Over 20 years ...",
        servicesTitle:"Services",
        services:["Injection mold design","Rubber mold design"],
        contactTitle:"Contact",
        contactText:"📍 Slovenia<br>📧 ...",
        footer:"© 2026 ..."
    },

    de: { 
        docsTitle: "Dokumente",
        documents: [
            {
                name: "Anforderungen für Werkzeugkonstruktion",
                url: "https://raw.githubusercontent.com/plegerm/plegerm.github.io/main/Zahteve%20za%20izdelavo%20konstrukcije.docx"
            }
        ],
        title:"KUNSTSTOFFTECHNIK",
        aboutTitle:"Über uns",
        aboutText:"Über 20 Jahre ...",
        servicesTitle:"Dienstleistungen",
        services:["Spritzguss...", "DFM erstellen"],
        contactTitle:"Kontakt",
        contactText:"📍 Slowenien<br>📧 ...",
        footer:"© 2026 ..."
    }
};

function setLang(lang) {
    const d = content[lang];

    document.getElementById("docsLabel").innerText = d.docsTitle;

    const dropdown = document.getElementById("docsDropdown");
    dropdown.innerHTML = "";

    d.documents.forEach(doc => {
        const a = document.createElement("a");
        a.innerText = doc.name;
        a.href = doc.url;
        a.target = "_blank";
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
