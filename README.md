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
