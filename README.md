# gameing
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>🎮 online games · arcade portal</title>
    <!-- Font Awesome 6 (free) for game icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, system-ui, sans-serif;
        }

        body {
            background: linear-gradient(145deg, #0b0f1c 0%, #1a1f33 100%);
            min-height: 100vh;
            color: #f0eef7;
        }

        /* header / navigation */
        .game-header {
            background: rgba(10, 14, 23, 0.85);
            backdrop-filter: blur(8px);
            padding: 1.2rem 2rem;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            border-bottom: 2px solid #3b3f6b;
            box-shadow: 0 8px 20px rgba(0,0,0,0.6);
            position: sticky;
            top: 0;
            z-index: 10;
        }

        .logo-area {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-icon {
            font-size: 2.4rem;
            color: #ffcc4d;
            filter: drop-shadow(0 0 6px #f0b340);
        }

        .logo-text {
            font-size: 1.9rem;
            font-weight: 700;
            background: linear-gradient(135deg, #f5d77e, #c5a1ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: 1px;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            font-weight: 500;
        }

        .nav-links a {
            color: #cacde8;
            text-decoration: none;
            font-size: 1.2rem;
            transition: 0.2s;
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .nav-links a i {
            font-size: 1rem;
            color: #a9b0e6;
        }

        .nav-links a:hover {
            color: #ffe074;
            text-shadow: 0 0 6px #ffb347;
        }

        .search-bar {
            background: #262b44;
            padding: 0.4rem 1rem;
            border-radius: 40px;
            display: flex;
            align-items: center;
            border: 1px solid #4c5180;
        }

        .search-bar i {
            color: #a9b0e6;
            font-size: 1.1rem;
        }

        .search-bar input {
            background: transparent;
            border: none;
            padding: 0.5rem 0.8rem;
            color: #f0eef7;
            font-size: 1rem;
            outline: none;
            min-width: 200px;
        }

        .search-bar input::placeholder {
            color: #7b81ac;
            font-style: italic;
        }

        /* main container */
        .container {
            max-width: 1400px;
            margin: 2rem auto;
            padding: 0 2rem;
        }

        /* hero banner */
        .hero-banner {
            background: linear-gradient(112deg, #202842, #2c2f55);
            border-radius: 2rem;
            padding: 2.2rem 2.5rem;
            margin-bottom: 3rem;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            border: 1px solid #595e93;
            box-shadow: 0 20px 30px -10px #070915;
        }

        .hero-text h2 {
            font-size: 2.8rem;
            font-weight: 800;
            line-height: 1.2;
        }

        .hero-text .highlight {
            color: #fedb7c;
            text-decoration: underline wavy #b37beb 3px;
        }

        .hero-text p {
            font-size: 1.3rem;
            margin-top: 0.8rem;
            color: #bcc2ec;
        }

        .hero-cta {
            background: #ff9f4b;
            border: none;
            color: #191e30;
            font-weight: 700;
            font-size: 1.4rem;
            padding: 0.9rem 2.2rem;
            border-radius: 3rem;
            display: flex;
            align-items: center;
            gap: 10px;
            cursor: pointer;
            transition: 0.2s;
            box-shadow: 0 10px 20px #b95f1d60;
        }

        .hero-cta i {
            font-size: 1.8rem;
        }

        .hero-cta:hover {
            background: #ffb86b;
            transform: scale(1.02);
            box-shadow: 0 12px 26px #ff9f4b80;
        }

        /* category filters */
        .category-row {
            display: flex;
            flex-wrap: wrap;
            gap: 0.8rem 1.5rem;
            margin: 2rem 0 2.5rem 0;
            justify-content: center;
        }

        .cat-chip {
            background: #262d47;
            padding: 0.6rem 1.5rem;
            border-radius: 40px;
            font-size: 1.1rem;
            font-weight: 500;
            color: #d6dcff;
            border: 1px solid #515b8a;
            transition: 0.15s;
            cursor: default;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .cat-chip i {
            color: #ffbc6c;
        }

        .cat-chip.active {
            background: #4d3b9f;
            border-color: #cfa15e;
            color: white;
            box-shadow: 0 0 12px #8965cf;
        }

        /* games grid */
        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
            gap: 2rem 1.5rem;
            margin: 3rem 0;
        }

        .game-card {
            background: #1d223b;
            border-radius: 2rem 2rem 1.8rem 1.8rem;
            overflow: hidden;
            border: 1px solid #3f4570;
            box-shadow: 0 18px 25px -12px #030413;
            transition: transform 0.2s, box-shadow 0.3s;
            backdrop-filter: blur(4px);
            display: flex;
            flex-direction: column;
        }

        .game-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 25px 35px -10px #161d40;
            border-color: #8d7fd1;
        }

        .card-img {
            height: 150px;
            background: #2c3153;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            font-size: 4rem;
            color: #b7bffa;
            border-bottom: 2px solid #3f4675;
        }

        .card-img .overlay-tag {
            position: absolute;
            top: 15px;
            right: 15px;
            background: #eb5f5fcc;
            backdrop-filter: blur(4px);
            padding: 0.2rem 1rem;
            border-radius: 30px;
            font-size: 0.8rem;
            font-weight: 600;
            color: white;
            border: 1px solid #ffacac;
        }

        .card-content {
            padding: 1.2rem 1rem 1.5rem;
            flex: 1;
            display: flex;
            flex-direction: column;
        }

        .game-title {
            font-size: 1.6rem;
            font-weight: 600;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .game-title i {
            color: #ffb86b;
            font-size: 1.3rem;
            opacity: 0.9;
        }

        .game-category {
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
            background: #2f355a;
            display: inline-block;
            padding: 0.2rem 1rem;
            border-radius: 30px;
            margin: 0.7rem 0 1rem 0;
            color: #bdc3f0;
            align-self: flex-start;
        }

        .game-desc {
            color: #bdc3ee;
            line-height: 1.5;
            font-size: 0.95rem;
            margin-bottom: 1.4rem;
            flex: 1;
        }

        .play-button {
            background: transparent;
            border: 2px solid #737bcb;
            color: #d9ddfc;
            padding: 0.6rem 0rem;
            border-radius: 2.5rem;
            font-weight: 600;
            font-size: 1.1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            transition: 0.2s;
            margin-top: 0.5rem;
            text-decoration: none;
            width: 100%;
        }

        .play-button i {
            color: #ffcd7e;
        }

        .play-button:hover {
            background: #7079db40;
            border-color: #ffbc6c;
            color: white;
            letter-spacing: 0.5px;
        }

        /* featured section */
        .featured-head {
            display: flex;
            align-items: baseline;
            justify-content: space-between;
            margin: 4rem 0 1rem 0;
        }

        .featured-head h3 {
            font-size: 2rem;
            font-weight: 500;
            border-left: 10px solid #fcb571;
            padding-left: 1.3rem;
        }

        .featured-head span {
            color: #b7c0f5;
            font-size: 1.1rem;
        }

        /* footer */
        .game-footer {
            background: #0e1222;
            margin-top: 5rem;
            padding: 2.5rem 2rem;
            border-top: 1px solid #3a3f68;
            text-align: center;
            color: #979dc9;
        }

        .footer-links {
            display: flex;
            flex-wrap: wrap;
            gap: 2rem;
            justify-content: center;
            margin: 1.5rem 0;
        }

        .footer-links a {
            color: #b7bef0;
            text-decoration: none;
            font-size: 1.1rem;
        }

        .footer-links a:hover {
            color: #f6cf7c;
        }

        hr {
            border: 0.5px solid #2f3452;
            margin: 1rem 0;
        }

        /* responsiveness */
        @media (max-width: 650px) {
            .game-header {
                flex-direction: column;
                gap: 1rem;
                align-items: stretch;
            }
            .logo-area {
                justify-content: center;
            }
            .nav-links {
                justify-content: center;
            }
            .search-bar {
                width: 100%;
            }
            .search-bar input {
                width: 100%;
            }
            .hero-text h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>

<header class="game-header">
    <div class="logo-area">
        <i class="fas fa-gamepad logo-icon"></i>
        <span class="logo-text">online games</span>
    </div>
    <div class="nav-links">
        <a href="#"><i class="fa-solid fa-compass"></i> Arcade</a>
        <a href="#"><i class="fa-solid fa-star"></i> New</a>
        <a href="#"><i class="fa-solid fa-trophy"></i> Leaderboard</a>
        <a href="#"><i class="fa-solid fa-user-group"></i> Friends</a>
    </div>
    <div class="search-bar">
        <i class="fa-solid fa-magnifying-glass"></i>
        <input type="text" placeholder="find your game ...">
    </div>
</header>

<main class="container">
    <!-- hero banner -->
    <div class="hero-banner">
        <div class="hero-text">
            <h2>🎯 instant play · <span class="highlight">no download</span></h2>
            <p>jump into 200+ free online games — challenge friends</p>
        </div>
        <button class="hero-cta"><i class="fa-solid fa-bolt"></i> random game</button>
    </div>

    <!-- category quick filters -->
    <div class="category-row">
        <div class="cat-chip active"><i class="fa-solid fa-border-all"></i> all games</div>
        <div class="cat-chip"><i class="fa-solid fa-car"></i> racing</div>
        <div class="cat-chip"><i class="fa-solid fa-puzzle-piece"></i> puzzle</div>
        <div class="cat-chip"><i class="fa-solid fa-people-group"></i> multiplayer</div>
        <div class="cat-chip"><i class="fa-solid fa-shield"></i> action</div>
        <div class="cat-chip"><i class="fa-solid fa-chess-queen"></i> strategy</div>
        <div class="cat-chip"><i class="fa-solid fa-basketball"></i> sports</div>
    </div>

    <!-- games grid (core content) -->
    <section class="games-grid">
        <!-- card 1 - classic arcade -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-ghost"></i>
                <span class="overlay-tag">HOT</span>
            </div>
            <div class="card-content">
                <div class="game-title">PAC-MAN <i class="fa-regular fa-circle-play"></i></div>
                <span class="game-category">ARCADE</span>
                <div class="game-desc">maze runner · eat dots, avoid ghosts. classic 1980 charm.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
        <!-- card 2 - racing -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-car-side"></i>
            </div>
            <div class="card-content">
                <div class="game-title">speed racers <i class="fa-regular fa-clock"></i></div>
                <span class="game-category">RACING</span>
                <div class="game-desc">drift on neon tracks. 4 players split-screen online.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
        <!-- card 3 - puzzle -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-cubes"></i>
                <span class="overlay-tag">−80%</span>
            </div>
            <div class="card-content">
                <div class="game-title">block collapse <i class="fa-regular fa-star"></i></div>
                <span class="game-category">PUZZLE</span>
                <div class="game-desc">match 3, chain reactions & powerups. 500 levels.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
        <!-- card 4 - multiplayer battle -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-crosshairs"></i>
            </div>
            <div class="card-content">
                <div class="game-title">laser strike <i class="fa-solid fa-wifi"></i></div>
                <span class="game-category">ACTION</span>
                <div class="game-desc">8‑player online arena. quick matches, upgrade guns.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
        <!-- card 5 - sports -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-futbol"></i>
            </div>
            <div class="card-content">
                <div class="game-title">super kick <i class="fa-regular fa-futbol"></i></div>
                <span class="game-category">SPORTS</span>
                <div class="game-desc">penalty shootout · curved shots & tournaments.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
        <!-- card 6 - strategy -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-chess-board"></i>
                <span class="overlay-tag">NEW</span>
            </div>
            <div class="card-content">
                <div class="game-title">king's valley <i class="fa-regular fa-gem"></i></div>
                <span class="game-category">STRATEGY</span>
                <div class="game-desc">build, siege, trade. online multiplayer kingdom.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
        <!-- card 7 - card game -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-club"></i>
            </div>
            <div class="card-content">
                <div class="game-title">solitaire tripeaks <i class="fa-regular fa-club"></i></div>
                <span class="game-category">CARDS</span>
                <div class="game-desc">classic klondike & adventure mode. daily challenges.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
        <!-- card 8 - io game -->
        <div class="game-card">
            <div class="card-img">
                <i class="fa-solid fa-otter"></i>
            </div>
            <div class="card-content">
                <div class="game-title">worm.io <i class="fa-regular fa-keyboard"></i></div>
                <span class="game-category">.IO</span>
                <div class="game-desc">grow by eating. 32 players real-time. chaotic fun.</div>
                <a href="#" class="play-button"><i class="fa-solid fa-play"></i> play now</a>
            </div>
        </div>
    </section>

    <!-- featured this week -->
    <div class="featured-head">
        <h3><i class="fa-regular fa-fire-flame-curved" style="color: #fcb571;"></i> featured online games</h3>
        <span>see all <i class="fa-solid fa-arrow-right"></i></span>
    </div>
    <div style="display: flex; gap: 1.2rem; flex-wrap: wrap; margin-bottom: 2rem;">
        <div style="background: #222845; border-radius: 2rem; padding: 1rem 2.5rem 1rem 2rem; border: 1px solid #6f7199; display: flex; align-items: center; gap: 1.2rem;">
            <i class="fa-solid fa-crown" style="font-size: 2.4rem; color: #f9d56f;"></i>
            <div><strong style="font-size: 1.4rem;">battle arena</strong><br> 12k players now</div>
        </div>
        <div style="background: #222845; border-radius: 2rem; padding: 1rem 2.5rem 1rem 2rem; border: 1px solid #6f7199; display: flex; align-items: center; gap: 1.2rem;">
            <i class="fa-solid fa-dragon" style="font-size: 2.4rem; color: #9e9eff;"></i>
            <div><strong style="font-size: 1.4rem;">dragons rise</strong><br> new expansion</div>
        </div>
    </div>

    <!-- info banner -->
    <div style="background: #1f2440; border-radius: 2rem; padding: 2rem; border: 1px solid #545c99; margin-top: 3rem; display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between;">
        <span><i class="fa-regular fa-circle-check" style="color: #80ffb2;"></i> 100% free · no signup required</span>
        <span><i class="fa-regular fa-clock"></i> instant play in browser</span>
        <span><i class="fa-regular fa-users"></i> 12k+ players online</span>
    </div>
</main>

<!-- footer -->
<footer class="game-footer">
    <div class="footer-links">
        <a href="#"><i class="fa-regular fa-compass"></i> arcade</a>
        <a href="#"><i class="fa-regular fa-star"></i> new games</a>
        <a href="#"><i class="fa-regular fa-message"></i> chat</a>
        <a href="#"><i class="fa-regular fa-circle-question"></i> help</a>
        <a href="#"><i class="fa-regular fa-flag"></i> report</a>
    </div>
    <hr>
    <p style="font-size: 0.95rem;">🎮 online games portal · retro & modern games. all trademarks belong to their owners.<br> 
    this is a demo concept — click any "play now" to imagine the fun!</p>
    <p style="margin-top: 1.2rem;">© 2025 · online games collective <i class="fa-regular fa-heart" style="color: #f97474;"></i></p>
</footer>

<!-- small interactive note (just for demonstration) -->
<script>
    (function() {
        // tiny console spirit: just to show we're alive
        console.log("🎮 online games hub — ready to play!");
        // optional: search bar non-functional, but keeps style
        const searchInput = document.querySelector('.search-bar input');
        searchInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                e.preventDefault();
                alert("🔍 demo: searching for '" + searchInput.value + "' (this is a static demo)");
            }
        });
        // random game button click hint
        document.querySelector('.hero-cta').addEventListener('click', () => {
            const games = ["PAC-MAN", "speed racers", "block collapse", "laser strike", "super kick", "king's valley", "solitaire", "worm.io"];
            const rand = games[Math.floor(Math.random() * games.length)];
            alert("🎲 random pick: " + rand + " — get ready to play!");
        });
        // make "play now" buttons show a playful message
        document.querySelectorAll('.play-button').forEach(btn => {
            btn.addEventListener('click', (e) => {
                e.preventDefault();
                const card = btn.closest('.game-card');
                const title = card?.querySelector('.game-title')?.innerText || 'this game';
                alert("✨ loading " + title + " (demo — actual game would start)");
            });
        });
        // category chips just visual feedback
        document.querySelectorAll('.cat-chip').forEach(chip => {
            chip.addEventListener('click', () => {
                document.querySelectorAll('.cat-chip').forEach(c => c.classList.remove('active'));
                chip.classList.add('active');
            });
        });
    })();
</script>
</body>
</html>
