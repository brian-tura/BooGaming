# 🎮 BooGaming — Piattaforma E-Commerce di Videogiochi

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-404D59?style=for-the-badge)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-008CDD?style=for-the-badge&logo=stripe&logoColor=white)

Piattaforma e-commerce full-stack per la consultazione e l'acquisto di videogiochi digitali, sviluppata come **progetto finale di gruppo** durante il Master intensivo in Full-Stack Web Development di **Boolean Careers**.

---

## 📸 Anteprima Store

<!-- Salva lo screenshot dello store come 'preview.png' nella cartella principale -->
![BooGaming Preview](preview.png)

---

## 🎯 Il Progetto

L'obiettivo del progetto era simulare un vero store digitale (in stile Steam / Epic Games) affrontando tutte le sfide di un'applicazione client-server completa:
* Gestione di un **database relazionale complesso** (relazioni molti-a-molti tra giochi, generi, piattaforme e ordini).
* Sviluppo di **API RESTful** in Node.js ed Express con query SQL native (prepared statements per prevenire SQL Injection).
* Frontend reattivo in **React** con gestione dei filtri in tempo reale, carrello dinamico e routing tramite slug.
* Integrazione reale del flusso di cassa e pagamento con **Stripe Checkout API**.

---

## ✨ Funzionalità Principali

* **Catalogo Dinamico (50+ Titoli):** Consultazione dei giochi con ordinamento per prezzo, data di uscita e ricerca testuale per nome.
* **Organizzazione Relazionale:**
  * Suddivisione dei titoli per **Publisher** reali (*Ubisoft, CD Projekt Red, EA, Nintendo, Sony, Capcom, Square Enix*).
  * Filtro per **Piattaforma** (*PC, PlayStation 5, Xbox Series X, Nintendo Switch*).
  * Categorizzazione per **Genere** (*GDR, Azione, Avventura, Sparatutto, Sport, Corse, Picchiaduro*).
* **Pagine Dettaglio con Slug:** Navigazione SEO-friendly basata sullo slug univoco del videogioco (es. `/videogames/the-witcher-3-wild-hunt`).
* **Sistema Carrello & Codici Sconto:**
  * Calcolo dinamico dei totali e subtotali con gestione delle offerte percentuali sui singoli giochi.
  * Motore di validazione sconti con verifica lato database su date di validità (`discounts`, es. codice `BOOLEAN20`).
* **Integrazione Stripe:** Generazione di sessioni di checkout sicure con `line_items` personalizzati e gestione dei metadata degli ordini.

---

## 🛠️ Stack Tecnologico

### Frontend:
* **React 18** (SPA con componenti modulari)
* **Vite** (Build tool e server di sviluppo)
* **Axios** (Chiamate HTTP asincrone verso il backend)
* **CSS moderno** (Layout responsive, dark mode, caroselli e card dedicate)

### Backend:
* **Node.js** (Runtime environment)
* **Express.js** (Routing, middleware personalizzati per CORS e gestione percorsi immagini)
* **mysql2** (Driver per connessione a MySQL con query parametrizzate)
* **Stripe SDK** (Integrazione pagamenti digitali)

### Database:
* **MySQL** (9 tabelle tra entità e tabelle ponte: `videogames`, `publishers`, `platforms`, `genres`, `discounts`, `orders`, `videogame_platform`, `videogame_genre`, `videogame_order`).

---

## ⚙️ Come Avviare il Progetto in Locale

### Prerequisiti
* **Node.js** (v18 o superiore)
* **MySQL** attivo in locale (XAMPP o MySQL Server)

---

### 1. Database Setup
1. Apri phpMyAdmin o MySQL Workbench.
2. Esegui il file SQL di ripopolamento: **`database_seed.sql`** presente nella cartella `/backend`.
3. Verrà creato il database `boogaming_db` completo di 50 videogiochi, generi, piattaforme e codici sconto attivi.

---

### 2. Avvio Backend (Node / Express)

Apri il terminale:
```bash
cd backend
npm install
```

Crea un file .env dentro la cartella backend con le seguenti variabili:
```bash
PORT=3000
FE_APP=http://localhost:5173


# Database MySQL
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=root   # Inserisci la tua password o lascia vuoto se non impostata
DB_NAME=boogaming_db
DB_PORT=3306

# Stripe (Chiave di test)
STRIPE_SECRET_KEY=sk_test_tuachiavestripe
```

Avvia il server:
```bash
npm start
```
Il server sarà attivo su: http://localhost:3000

3. Avvio Frontend (React / Vite)
Apri un secondo terminale:
```bash
cd frontend
npm install
npm run dev
```

Apri il browser su: 👉 http://localhost:5173
👥 Autori
Progetto di gruppo finale realizzato durante il corso Boolean Careers da:
Brian Tura e colleghi — Full-Stack Developer (GitHub | LinkedIn)
Team di sviluppo Boolean Careers