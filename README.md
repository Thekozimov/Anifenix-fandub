<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Anifenix | Dublyaj Olami</title>
    <link rel="stylesheet" href="style.css">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;700;900&display=swap" rel="stylesheet">
</head>
<body>

    <nav class="navbar">
        <div class="logo">Ani<span>fenix</span></div>
        <div class="nav-links">
            <button class="nav-btn active" onclick="openTab('home')">Asosiy</button>
            <button class="nav-btn" onclick="openTab('releases')">Premyeralar</button>
            <button class="nav-btn" onclick="openTab('team')">Jamoa</button>
        </div>
    </nav>

    <main class="content">
        <section id="home" class="tab-content active">
            <div class="hero-box">
                <h1 class="glow-text">Anifenix</h1>
                <p>O'zbek tilidagi eng sifatli dublyajlar platformasi.</p>
                <div class="hero-stats">
                    <span><b>50+</b> Anime</span>
                    <span><b>1000+</b> Muxlis</span>
                </div>
                <button class="cta-btn" onclick="openTab('releases')">Tomosha qilish</button>
            </div>
        </section>

        <section id="releases" class="tab-content">
            <h2 class="title">Yangi Chiqishlar</h2>
            <div class="anime-grid">
                <div class="anime-card">
                    <span class="status">HD</span>
                    <div class="img-wrapper">
                        <img src="https://www.pngplay.com/wp-content/uploads/12/Jujutsu-Kaisen-Satoru-Gojo-PNG-Clipart-Background.png" class="png-img">
                    </div>
                    <h4>Jujutsu Kaisen</h4>
                    <p>2-fasl 15-qism</p>
                </div>
                <div class="anime-card">
                    <span class="status">New</span>
                    <div class="img-wrapper">
                        <img src="https://static.wikia.nocookie.net/kimetsu-no-yaiba/images/6/60/Tanjiro_Kamado_Anime_Design.png" class="png-img">
                    </div>
                    <h4>Demon Slayer</h4>
                    <p>4-fasl 1-qism</p>
                </div>
            </div>
        </section>

        <section id="team" class="tab-content">
            <h2 class="title">Ijodiy Jamoa</h2>
            <div class="team-container">
                <div class="member">
                    <div class="mic-icon">🎤</div>
                    <h3>M.Qobulov</h3>
                    <p>Dublyaj Ustasi</p>
                </div>
                <div class="member">
                    <div class="mic-icon">🎧</div>
                    <h3>SoundMaster</h3>
                    <p>Ovoz Rejisso'ri</p>
                </div>
            </div>
        </section>
    </main>

    <script src="script.js"></script>
</body>
</html>
* { margin: 0; padding: 0; box-sizing: border-box; }
body {
    background-color: #050505;
    color: white;
    font-family: 'Poppins', sans-serif;
    overflow-x: hidden;
}

/* Navbar */
.navbar {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 20px 8%;
    background: rgba(0,0,0,0.9);
    position: sticky;
    top: 0;
    z-index: 100;
    border-bottom: 1px solid rgba(255, 62, 62, 0.2);
}

.logo { font-size: 1.8rem; font-weight: 900; }
.logo span { color: #ff3e3e; text-shadow: 0 0 10px #ff3e3e; }

.nav-btn {
    background: none; border: none; color: #888;
    font-size: 1rem; margin-left: 20px; cursor: pointer;
    transition: 0.3s; font-weight: 600;
}

.nav-btn.active, .nav-btn:hover { color: #ff3e3e; }

/* Oynalar boshqaruvi */
.tab-content {
    display: none;
    padding: 40px 8%;
    animation: slideIn 0.5s ease forwards;
}

.tab-content.active { display: block; }

@keyframes slideIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
}

/* Hero Section */
.hero-box {
    text-align: center; padding: 100px 0;
    background: radial-gradient(circle, rgba(255, 62, 62, 0.1) 0%, transparent 70%);
}

.glow-text { font-size: 4rem; text-transform: uppercase; margin-bottom: 10px; }

.cta-btn {
    margin-top: 30px; padding: 15px 40px;
    background: #ff3e3e; border: none; color: white;
    border-radius: 50px; font-weight: bold; cursor: pointer;
    box-shadow: 0 0 20px rgba(255, 62, 62, 0.4);
}

/* Anime Kartalari */
.anime-grid {
    display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 30px;
}

.anime-card {
    background: #111; padding: 20px; border-radius: 20px;
    text-align: center; position: relative; border: 1px solid #222;
}

.img-wrapper {
    height: 250px; display: flex; align-items: center; justify-content: center;
}

.png-img {
    max-height: 100%; transition: 0.4s;
    filter: drop-shadow(0 5px 15px rgba(0,0,0,0.8));
}

.anime-card:hover .png-img {
    transform: scale(1.1) translateY(-10px);
    filter: drop-shadow(0 0 20px rgba(255, 62, 62, 0.5));
}

.status {
    position: absolute; top: 15px; left: 15px;
    background: #ff3e3e; font-size: 0.7rem; padding: 4px 10px; border-radius: 5px;
}

/* Jamoa */
.team-container { display: flex; gap: 20px; flex-wrap: wrap; }
.member {
    background: #111; padding: 40px; border-radius: 25px;
    flex: 1; min-width: 250px; text-align: center;
}
.mic-icon { font-size: 3rem; margin-bottom: 15px; }
function openTab(tabId) {
    // 1. Barcha oynalarni yashirish
    const tabs = document.querySelectorAll('.tab-content');
    tabs.forEach(tab => {
        tab.classList.remove('active');
    });

    // 2. Barcha tugmalardan 'active' klassini olib tashlash
    const buttons = document.querySelectorAll('.nav-btn');
    buttons.forEach(btn => {
        btn.classList.remove('active');
    });

    // 3. Tanlangan oynani ko'rsatish
    const activeTab = document.getElementById(tabId);
    activeTab.classList.add('active');

    // 4. Bosilgan tugmani rangini o'zgartirish
    // Event orqali tugmani topish
    const clickedBtn = Array.from(buttons).find(btn => 
        btn.getAttribute('onclick').includes(tabId)
    );
    if (clickedBtn) clickedBtn.classList.add('active');
    
    // Sahifani tepasiga qaytarish (agar kerak bo'lsa)
    window.scrollTo(0, 0);
}
