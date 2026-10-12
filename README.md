```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Little World</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Pirata+One&family=IM+Fell+English:ital@0;1&display=swap" rel="stylesheet">

<style>
:root {
    --ink: #10151c;
    --blue: #173b59;
    --wave: #245b7a;
    --paper: #f0e8d7;
    --white: #fffaf0;
}

* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

html {
    scroll-behavior: smooth;
}

body {
    background-color: var(--paper);
    color: var(--ink);
    font-family: 'IM Fell English', serif;
    min-height: 100vh;
    overflow-x: hidden;
}

/* Wave background */
body::before {
    content: "";
    position: fixed;
    inset: 0;
    z-index: -2;
    background-image:
        linear-gradient(
            rgba(240, 232, 215, 0.74),
            rgba(240, 232, 215, 0.74)
        ),
        url("https://upload.wikimedia.org/wikipedia/commons/a/a5/Tsunami_by_hokusai_19th_century.jpg");
    background-size: cover;
    background-position: center;
    background-attachment: fixed;
}

/* Navigation */
nav {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 12px;
    padding: 20px 12px;
    background: rgba(240, 232, 215, 0.92);
    border-bottom: 2px solid var(--ink);
    position: sticky;
    top: 0;
    z-index: 10;
}

nav button {
    font-family: 'Pirata One', cursive;
    font-size: 1.4rem;
    color: var(--ink);
    border: none;
    background: transparent;
    padding: 8px 12px;
    cursor: pointer;
    transition: 0.2s;
}

nav button:hover,
nav button.active {
    color: var(--wave);
    text-decoration: underline;
    text-underline-offset: 6px;
}

/* Main content */
main {
    max-width: 1000px;
    width: 92%;
    margin: 45px auto;
}

.page {
    display: none;
    animation: appear 0.5s ease;
}

.page.active {
    display: block;
}

@keyframes appear {
    from {
        opacity: 0;
        transform: translateY(10px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.panel {
    background: rgba(240, 232, 215, 0.91);
    border: 2px solid var(--ink);
    padding: clamp(22px, 5vw, 55px);
    box-shadow: 8px 8px 0 rgba(16, 21, 28, 0.2);
}

h1, h2, h3 {
    font-family: 'Pirata One', cursive;
    font-weight: normal;
}

h1 {
    font-size: clamp(3rem, 8vw, 6rem);
    line-height: 1.05;
    margin-bottom: 20px;
}

h2 {
    font-size: clamp(2.2rem, 5vw, 3.5rem);
    margin-bottom: 20px;
}

h3 {
    font-size: 1.8rem;
    margin-bottom: 10px;
}

p {
    font-size: 1.15rem;
    line-height: 1.8;
    margin-bottom: 18px;
}

.divider {
    text-align: center;
    font-size: 1.7rem;
    margin: 20px 0;
    color: var(--wave);
}

.small-title {
    letter-spacing: 3px;
    text-transform: uppercase;
    font-size: 0.8rem;
    margin-bottom: 18px;
}

/* Home */
.hero {
    min-height: 420px;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.hero p {
    max-width: 600px;
}

.button {
    display: inline-block;
    background: var(--ink);
    color: var(--white);
    border: 1px solid var(--ink);
    padding: 13px 22px;
    font-family: 'IM Fell English', serif;
    font-size: 1rem;
    text-decoration: none;
    cursor: pointer;
    margin: 8px 8px 8px 0;
    transition: 0.2s;
}

.button:hover {
    background: var(--wave);
    transform: translateY(-2px);
}

/* About cards */
.grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 18px;
    margin-top: 25px;
}

.card {
    border: 1px solid var(--ink);
    padding: 22px;
    background: rgba(255, 250, 240, 0.55);
}

.card p {
    margin-bottom: 0;
}

/* Playlist */
.song {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 15px;
    padding: 15px 0;
    border-bottom: 1px solid rgba(16, 21, 28, 0.3);
}

.song:last-child {
    border-bottom: none;
}

.song-name {
    font-size: 1.1rem;
}

.song-artist {
    font-size: 0.95rem;
    font-style: italic;
}

.song a {
    color: var(--blue);
    font-weight: bold;
    white-space: nowrap;
}

/* Social links */
.socials {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 15px;
    margin-top: 25px;
}

.social-link {
    display: block;
    padding: 18px;
    text-align: center;
    border: 1px solid var(--ink);
    text-decoration: none;
    color: var(--ink);
    background: rgba(255, 250, 240, 0.6);
    font-size: 1.15rem;
    transition: 0.2s;
}

.social-link:hover {
    background: var(--ink);
    color: var(--white);
    transform: translateY(-3px);
}

footer {
    text-align: center;
    padding: 30px 15px;
    font-size: 0.95rem;
}

/* Phone layout */
@media (max-width: 600px) {
    nav {
        gap: 2px;
        padding: 12px 5px;
    }

    nav button {
        font-size: 1.2rem;
        padding: 8px;
    }

    main {
        width: 94%;
        margin: 22px auto;
    }

    .grid,
    .socials {
        grid-template-columns: 1fr;
    }

    .panel {
        padding: 23px 18px;
    }

    .hero {
        min-height: 350px;
    }

    .song {
        align-items: flex-start;
    }
}

@media (prefers-reduced-motion: reduce) {
    *, *::before, *::after {
        animation: none !important;
        scroll-behavior: auto !important;
        transition: none !important;
    }
}
</style>
</head>

<body>

<nav aria-label="Main navigation">
    <button class="active" data-page="home">Home</button>
    <button data-page="about">About Me</button>
    <button data-page="playlist">Playlist</button>
    <button data-page="links">My Links</button>
</nav>

<main>

    <!-- HOME PAGE -->
    <section id="home" class="page active">
        <div class="panel hero">
            <div class="small-title">ようこそ · Welcome to my world</div>

            <h1>My Little<br>World.</h1>

            <div class="divider">✦ ── ♱ ── ✦</div>

            <p>
                Just a girl with a thousand thoughts,
                a love for music, anime, motorcycles,
                crocheting, and the little things in life.
            </p>

            <p>
                A little mysterious, a little chaotic,
                and always becoming someone new.
            </p>

            <div>
                <button class="button" data-go="about">
                    Discover my world ↗
                </button>

                <button class="button" data-go="links">
                    Find me elsewhere ↗
                </button>
            </div>
        </div>
    </section>

    <!-- ABOUT PAGE -->
    <section id="about" class="page">
        <div class="panel">
            <div class="small-title">A page from my diary</div>
            <h2>A Little About Me</h2>

            <p>
                Hello, stranger. Welcome to my corner of the internet.
                This is where I keep a little piece of who I am.
            </p>

            <div class="divider">✦</div>

            <div class="grid">
                <div class="card">
                    <h3>♡ My Interests</h3>
                    <p>
                        Anime, manhwa, music, gaming,
                        crocheting, writing, and motorcycles.
                    </p>
                </div>

                <div class="card">
                    <h3>☾ My Personality</h3>
                    <p>
                        A quiet soul with a busy mind.
                        I enjoy meaningful conversations,
                        creativity, and having my own space.
                    </p>
                </div>

                <div class="card">
                    <h3>✧ My Dreams</h3>
                    <p>
                        Learning new things, improving my skills,
                        creating things of my own, and exploring
                        the possibilities ahead of me.
                    </p>
                </div>

                <div class="card">
                    <h3>♱ My Little Things</h3>
                    <p>
                        Late-night music, beautiful stories,
                        handmade projects, and finding beauty
                        in the smallest details.
                    </p>
                </div>
            </div>

            <div class="divider">── ✧ ──</div>

            <h3>A note from me</h3>
            <p>
                I'm still figuring things out, learning who I am,
                and growing at my own pace. There's always more
                to a person than what you see on the surface.
            </p>
        </div>
    </section>

    <!-- PLAYLIST PAGE -->
    <section id="playlist" class="page">
        <div class="panel">
            <div class="small-title">The soundtrack to my mind</div>
            <h2>My Playlist ♫</h2>

            <p>
                Songs I love, songs I replay, and songs
                that feel like little pieces of me.
            </p>

            <p>
                Replace these example songs with your favourites.
                Use the links to open each song.
            </p>

            <div class="divider">♪ ── ♫ ── ♪</div>

            <div class="song">
                <div>
                    <div class="song-name">LOOK DON'T TOUCH</div>
                    <div class="song-artist">Odetari</div>
                </div>
                <a href="https://open.spotify.com/search/LOOK%20DON'T%20TOUCH%20Odetari"
                   target="_blank" rel="noopener noreferrer">Listen ↗</a>
            </div>

            <div class="song">
                <div>
                    <div class="song-name">Add your song</div>
                    <div class="song-artist">Artist name</div>
                </div>
                <a href="https://open.spotify.com/"
                   target="_blank" rel="noopener noreferrer">Listen ↗</a>
            </div>

            <div class="song">
                <div>
                    <div class="song-name">Add your song</div>
                    <div class="song-artist">Artist name</div>
                </div>
                <a href="https://open.spotify.com/"
                   target="_blank" rel="noopener noreferrer">Listen ↗</a>
            </div>

            <div class="song">
                <div>
                    <div class="song-name">Add your song</div>
                    <div class="song-artist">Artist name</div>
                </div>
                <a href="https://open.spotify.com/"
                   target="_blank" rel="noopener noreferrer">Listen ↗</a>
            </div>

            <div class="divider">✧</div>

            <a class="button"
               href="https://open.spotify.com/"
               target="_blank" rel="noopener noreferrer">
                Open Spotify ↗
            </a>
        </div>
    </section>

    <!-- SOCIAL LINKS PAGE -->
    <section id="links" class="page">
        <div class="panel">
            <div class="small-title">Across the internet</div>
            <h2>Find Me Here</h2>

            <p>
                Want to find me somewhere else?
                Here are my social links.
            </p>

            <div class="divider">✦ ♡ ✦</div>

            <div class="socials">
                <a class="social-link"
                   href="https://www.instagram.com/"
                   target="_blank" rel="noopener noreferrer">
                    Instagram ↗
                </a>

                <a class="social-link"
                   href="https://www.tiktok.com/"
                   target="_blank" rel="noopener noreferrer">
                    TikTok ↗
                </a>

                <a class="social-link"
                   href="https://www.youtube.com/"
                   target="_blank" rel="noopener noreferrer">
                    YouTube ↗
                </a>

                <a class="social-link"
                   href="https://open.spotify.com/"
                   target="_blank" rel="noopener noreferrer">
                    Spotify ↗
                </a>

                <a class="social-link"
                   href="https://www.pinterest.com/"
                   target="_blank" rel="noopener noreferrer">
                    Pinterest ↗
                </a>

                <a class="social-link"
                   href="https://www.roblox.com/"
                   target="_blank" rel="noopener noreferrer">
                    Roblox ↗
                </a>
            </div>

            <div class="divider">── ♱ ──</div>

            <p>
                Remember to replace the example links with your
                own profile URLs so people can find your accounts.
            </p>
        </div>
    </section>

</main>

<footer>
    <p>Made with ♡ and a little darkness.</p>
    <p>✧ Welcome to my little corner of the universe ✧</p>
</footer>

<script>
const navButtons = document.querySelectorAll("nav button");
const pages = document.querySelectorAll(".page");

function showPage(pageId) {
    const target = document.getElementById(pageId);

    if (!target) return;

    pages.forEach(page => {
        page.classList.toggle("active", page.id === pageId);
    });

    navButtons.forEach(button => {
        const selected = button.dataset.page === pageId;

        button.classList.toggle("active", selected);

        if (selected) {
            button.setAttribute("aria-current", "page");
        } else {
            button.removeAttribute("aria-current");
        }
    });

    history.replaceState(null, "", "#" + pageId);
    window.scrollTo({ top: 0, behavior: "smooth" });
}

navButtons.forEach(button => {
    button.addEventListener("click", () => {
        showPage(button.dataset.page);
    });
});

document.querySelectorAll("[data-go]").forEach(button => {
    button.addEventListener("click", () => {
        showPage(button.dataset.go);
    });
});

const initialPage = location.hash.slice(1);

if (document.getElementById(initialPage)?.classList.contains("page")) {
    showPage(initialPage);
}
</script>

</body>
</html>
```
