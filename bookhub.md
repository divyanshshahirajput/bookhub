# bookhub
Create a single, unified platform that lets students and author seamlessly access digital e-books  records — anytime, from anywhere on platform
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bookhub &mdash; E-Book Store</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,wght@0,400;0,500;0,600;1,400&family=Work+Sans:wght@400;500;600&display=swap" rel="stylesheet">
<style>
/* ---------------------------------------------------
   Inkwell — E-Book Store
   Tokens
--------------------------------------------------- */
:root{
  --ink-black:   #14201c;
  --forest-deep: #0d1512;
  --paper:       #efe6d3;
  --paper-dim:   #e3d8bf;
  --brass:       #b78a3d;
  --brass-light: #d3ab5f;
  --rust:        #9c4a2e;
  --text-dark:   #1f2a22;
  --text-soft:   #4c5850;

  --serif: "Fraunces", Georgia, "Times New Roman", serif;
  --sans: "Work Sans", -apple-system, "Segoe UI", sans-serif;

  --radius: 4px;
  --max: 1120px;
}

*{ box-sizing: border-box; }

html{ scroll-behavior: smooth; }

body{
  margin: 0;
  background: var(--paper);
  color: var(--text-dark);
  font-family: var(--sans);
  font-size: 16px;
  line-height: 1.55;
}

img{ max-width: 100%; display: block; }

.wrap{
  max-width: var(--max);
  margin: 0 auto;
  padding: 0 28px;
}

h1, h2, h3, blockquote{
  font-family: var(--serif);
  font-weight: 500;
  margin: 0 0 0.5em 0;
  color: var(--ink-black);
}

a{ color: inherit; text-decoration: none; }

.sr-only{
  position: absolute;
  width: 1px; height: 1px;
  overflow: hidden;
  clip: rect(0 0 0 0);
}

/* ---------------------------------------------------
   Buttons
--------------------------------------------------- */
.btn{
  display: inline-block;
  padding: 13px 26px;
  border-radius: var(--radius);
  font-family: var(--sans);
  font-weight: 600;
  font-size: 0.95rem;
  border: 1px solid transparent;
  cursor: pointer;
  transition: background 0.15s ease, color 0.15s ease, border-color 0.15s ease;
}

.btn-primary{
  background: var(--rust);
  color: var(--paper);
}
.btn-primary:hover{ background: #86402a; }

.btn-ghost{
  background: transparent;
  color: var(--ink-black);
  border-color: var(--ink-black);
}
.btn-ghost:hover{ background: var(--ink-black); color: var(--paper); }

.btn-add{
  background: transparent;
  border: 1px solid var(--ink-black);
  color: var(--ink-black);
  padding: 8px 16px;
  border-radius: var(--radius);
  font-family: var(--sans);
  font-weight: 600;
  font-size: 0.82rem;
  cursor: pointer;
  transition: background 0.15s ease, color 0.15s ease;
}
.btn-add:hover{ background: var(--ink-black); color: var(--paper); }

/* ---------------------------------------------------
   Header
--------------------------------------------------- */
.site-header{
  position: sticky;
  top: 0;
  z-index: 10;
  background: var(--paper);
  border-bottom: 1px solid rgba(20,32,28,0.12);
}

.header-inner{
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 18px;
  padding-bottom: 18px;
}

.brand{
  font-family: var(--serif);
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--ink-black);
}

.main-nav{
  display: flex;
  gap: 32px;
}
.main-nav a{
  font-size: 0.95rem;
  font-weight: 500;
  color: var(--text-soft);
  border-bottom: 1px solid transparent;
  padding-bottom: 2px;
}
.main-nav a:hover{ color: var(--ink-black); border-color: var(--brass); }

.header-actions{
  display: flex;
  align-items: center;
  gap: 20px;
  font-size: 0.9rem;
}
.icon-link{ color: var(--text-soft); }
.icon-link:hover{ color: var(--ink-black); }

.cart-pill{
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: var(--ink-black);
  color: var(--paper);
  padding: 8px 14px;
  border-radius: 999px;
  font-weight: 600;
}
.cart-count{
  background: var(--brass);
  color: var(--ink-black);
  border-radius: 999px;
  padding: 1px 8px;
  font-size: 0.78rem;
}

/* ---------------------------------------------------
   Hero
--------------------------------------------------- */
.hero{
  padding: 84px 0 96px;
}

.hero-inner{
  display: grid;
  grid-template-columns: 1.1fr 0.9fr;
  gap: 56px;
  align-items: center;
}

.hero-copy h1{
  font-size: clamp(2.3rem, 4vw, 3.4rem);
  line-height: 1.08;
  letter-spacing: -0.01em;
}

.hero-sub{
  max-width: 46ch;
  color: var(--text-soft);
  font-size: 1.05rem;
  margin-bottom: 32px;
}

.hero-actions{
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}

.hero-art{
  display: flex;
  align-items: flex-end;
  justify-content: center;
  gap: 14px;
  height: 320px;
}

.book{
  width: 74px;
  border-radius: 3px 6px 6px 3px;
  box-shadow: -6px 8px 18px rgba(13,21,18,0.25);
  display: flex;
  align-items: flex-end;
  padding: 16px 10px;
  position: relative;
}
.book span{
  writing-mode: vertical-rl;
  transform: rotate(180deg);
  font-family: var(--serif);
  font-style: italic;
  font-size: 0.82rem;
  color: rgba(239,230,211,0.92);
}
.book-1{ height: 260px; background: var(--ink-black); }
.book-2{ height: 300px; background: var(--rust); }
.book-3{ height: 220px; background: var(--brass); }
.book-3 span{ color: var(--ink-black); }
.book-4{ height: 275px; background: var(--forest-deep); }

/* ---------------------------------------------------
   Section heads
--------------------------------------------------- */
.section-head{
  max-width: 50ch;
  margin-bottom: 40px;
}
.section-head h2{
  font-size: 1.9rem;
}
.section-head p{
  color: var(--text-soft);
  margin: 0;
}

/* ---------------------------------------------------
   Shelf / book grid
--------------------------------------------------- */
.shelf{
  padding: 40px 0 96px;
}

.book-grid{
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 28px;
}

.card{
  background: transparent;
}

.cover{
  height: 220px;
  border-radius: var(--radius);
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
  padding: 18px;
  box-shadow: 0 10px 22px rgba(13,21,18,0.18);
  margin-bottom: 14px;
}
.cover-title{
  font-family: var(--serif);
  font-style: italic;
  font-size: 1.15rem;
  color: var(--paper);
  line-height: 1.25;
}
.cover-author{
  font-size: 0.78rem;
  color: rgba(239,230,211,0.75);
  margin-top: 6px;
}

.cover-a{ background: linear-gradient(160deg, #22352c, var(--ink-black)); }
.cover-b{ background: linear-gradient(160deg, #b1583a, var(--rust)); }
.cover-c{ background: linear-gradient(160deg, #d3ab5f, var(--brass)); }
.cover-c .cover-title, .cover-c .cover-author{ color: var(--ink-black); }
.cover-d{ background: linear-gradient(160deg, #223a3c, #12211f); }
.cover-e{ background: linear-gradient(160deg, #6a4326, #46281a); }
.cover-f{ background: linear-gradient(160deg, #495f43, #253023); }

.card h3{
  font-size: 1.1rem;
  margin-bottom: 2px;
}
.card-author{
  color: var(--text-soft);
  font-size: 0.88rem;
  margin: 0 0 12px 0;
}
.card-meta{
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.price{
  font-family: var(--serif);
  font-size: 1.05rem;
  color: var(--ink-black);
}

/* ---------------------------------------------------
   Genres
--------------------------------------------------- */
.genres{
  padding: 40px 0 96px;
}
.genre-row{
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
}
.genre-tag{
  border: 1px solid rgba(20,32,28,0.22);
  padding: 10px 20px;
  border-radius: 999px;
  font-size: 0.92rem;
  font-weight: 500;
  color: var(--text-dark);
  transition: border-color 0.15s ease, background 0.15s ease;
}
.genre-tag:hover{
  border-color: var(--brass);
  background: rgba(183,138,61,0.12);
}

/* ---------------------------------------------------
   Quote band
--------------------------------------------------- */
.quote-band{
  background: var(--ink-black);
  color: var(--paper);
  padding: 88px 0;
}
.quote-inner{
  max-width: 720px;
}
.quote-band blockquote{
  color: var(--paper);
  font-style: italic;
  font-size: clamp(1.5rem, 3vw, 2.1rem);
  line-height: 1.35;
  margin: 0 0 18px 0;
}
.quote-attr{
  color: var(--brass-light);
  font-size: 0.92rem;
  margin: 0 0 36px 0;
}
.about-copy{
  color: rgba(239,230,211,0.78);
  font-size: 1.02rem;
  max-width: 60ch;
  margin: 0;
}

/* ---------------------------------------------------
   Newsletter
--------------------------------------------------- */
.newsletter{
  padding: 88px 0;
}
.newsletter-inner{
  display: grid;
  grid-template-columns: 1.1fr 1fr;
  gap: 40px;
  align-items: center;
  background: var(--paper-dim);
  border: 1px solid rgba(20,32,28,0.15);
  border-radius: 8px;
  padding: 48px;
}
.newsletter-inner p{
  color: var(--text-soft);
  margin: 8px 0 0 0;
}
.newsletter-form{
  display: flex;
  gap: 12px;
}
.newsletter-form input{
  flex: 1;
  padding: 13px 16px;
  border: 1px solid rgba(20,32,28,0.25);
  border-radius: var(--radius);
  font-family: var(--sans);
  font-size: 0.95rem;
  background: var(--paper);
  color: var(--text-dark);
}
.newsletter-form input:focus{
  outline: 2px solid var(--brass);
  outline-offset: 1px;
}

/* ---------------------------------------------------
   Footer
--------------------------------------------------- */
.site-footer{
  background: var(--forest-deep);
  color: rgba(239,230,211,0.85);
  padding-top: 64px;
}
.footer-inner{
  display: grid;
  grid-template-columns: 1.4fr 1fr 1fr 1fr;
  gap: 32px;
  padding-bottom: 48px;
}
.footer-brand .brand{ color: var(--paper); }
.footer-brand p{
  color: rgba(239,230,211,0.6);
  font-size: 0.9rem;
  margin-top: 10px;
  max-width: 26ch;
}
.footer-col h4{
  font-family: var(--sans);
  font-size: 0.85rem;
  font-weight: 600;
  color: var(--brass-light);
  margin: 0 0 14px 0;
}
.footer-col a{
  display: block;
  font-size: 0.92rem;
  color: rgba(239,230,211,0.75);
  margin-bottom: 10px;
}
.footer-col a:hover{ color: var(--paper); }

.footer-bottom{
  border-top: 1px solid rgba(239,230,211,0.12);
  padding: 22px 28px;
  font-size: 0.82rem;
  color: rgba(239,230,211,0.5);
}

/* ---------------------------------------------------
   Responsive
--------------------------------------------------- */
@media (max-width: 900px){
  .main-nav{ display: none; }
  .hero-inner{ grid-template-columns: 1fr; }
  .hero-art{ height: 220px; }
  .book-grid{ grid-template-columns: repeat(2, 1fr); }
  .newsletter-inner{ grid-template-columns: 1fr; padding: 32px; }
  .footer-inner{ grid-template-columns: 1fr 1fr; }
}

@media (max-width: 560px){
  .wrap{ padding: 0 20px; }
  .book-grid{ grid-template-columns: 1fr; }
  .header-actions .icon-link{ display: none; }
  .newsletter-form{ flex-direction: column; }
  .footer-inner{ grid-template-columns: 1fr; }
}

</style>
</head>
<body>

<header class="site-header">
  <div class="wrap header-inner">
    <a href="#top" class="brand">BOOKHUB</a>
    <nav class="main-nav">
      <a href="#shelf">Shop</a>
      <a href="#genres">Genres</a>
      <a href="#about">About</a>
      <a href="#newsletter">Contact</a>
    </nav>
    <div class="header-actions">
      <a href="#" class="icon-link" aria-label="Search">Search</a>
      <a href="#" class="cart-pill">Cart <span class="cart-count">0</span></a>
    </div>
  </div>
</header>

<main id="top">

  <!-- HERO -->
  <section class="hero">
    <div class="wrap hero-inner">
      <div class="hero-copy">
        <h1>Carry a whole library<br>in your pocket.</h1>
        <p class="hero-sub">Inkwell is a small shop for e-books &mdash; new releases, old favourites,
        and a few strange little finds you won't see anywhere else. Every title
        delivered straight to your reader in seconds.</p>
        <div class="hero-actions">
          <a href="#shelf" class="btn btn-primary">Browse the shelf</a>
          <a href="#about" class="btn btn-ghost">Why bookhub</a>
        </div>
      </div>
      <div class="hero-art" aria-hidden="true">
        <div class="book book-1"><span>MATH 4</span></div>
        <div class="book book-2"><span>COMPUTER ORGANIZATION & ARCH</span></div>
        <div class="book book-3"><span>HTML & CSS</span></div>
        <div class="book book-4"><span>DSTL</span></div>
      </div>
    </div>
  </section>

  <!-- FEATURED SHELF -->
  <section class="shelf" id="shelf">
    <div class="wrap">
      <div class="section-head">
        <h2>This week on the shelf</h2>
        <p>A short, changing selection &mdash; picked, not algorithmic.</p>
      </div>

      <div class="book-grid">

        <article class="card">
          <div class="cover cover-a">
            <span class="cover-title">MATH 4</span>
            <span class="cover-author">S.CHAND</span>
          </div>
          <div class="card-body">
            <h3>MATH 4</h3>
            <p class="card-author">S.CHAND</p>
            <div class="card-meta">
              <span class="price">FREE</span>
              <button class="btn-add" type="button">Add to cart</button>
            </div>
          </div>
        </article>

        <article class="card">
          <div class="cover cover-b">
            <span class="cover-title">COMPUTER ORGANIZATION & ARCH</span>
            <span class="cover-author">DR. Ashutosh kr .Roa</span>
          </div>
          <div class="card-body">
            <h3>COMPUTER ORGANIZATION & ARCH</h3>
            <p class="card-author">DR. Ashutosh kr .Roa</p>
            <div class="card-meta">
              <span class="price">FREE</span>
              <button class="btn-add" type="button">Add to cart</button>
            </div>
          </div>
        </article>

        <article class="card">
          <div class="cover cover-c">
            <span class="cover-title">HTML & CSS</span>
            <span class="cover-author">ISHIKA SHUKLA</span>
          </div>
          <div class="card-body">
            <h3>HTML & CSS</h3>
            <p class="card-author">ISHIKA SHUKLA</p>
            <div class="card-meta">
              <span class="price">FREE</span>
              <button class="btn-add" type="button">Add to cart</button>
            </div>
          </div>
        </article>

        <article class="card">
          <div class="cover cover-d">
            <span class="cover-title">DSTL</span>
            <span class="cover-author">SHUBHAM SRIVASTAV</span>
          </div>
          <div class="card-body">
            <h3>DSTL</h3>
            <p class="card-author">SHUBHAM SRIVASTAV</p>
            <div class="card-meta">
              <span class="price">FREE</span>
              <button class="btn-add" type="button">Add to cart</button>
            </div>
          </div>
        </article>

        <article class="card">
          <div class="cover cover-e">
            <span class="cover-title">LOVE STORY</span>
            <span class="cover-author">RAM JI</span>
          </div>
          <div class="card-body">
            <h3>LOVE STORY</h3>
            <p class="card-author">RAM JI</p>
            <div class="card-meta">
              <span class="price">₹7.25</span>
              <button class="btn-add" type="button">Add to cart</button>
            </div>
          </div>
        </article>

        <article class="card">
          <div class="cover cover-f">
            <span class="cover-title">LOVE AND WAR</span>
            <span class="cover-author">Dss</span>
          </div>
          <div class="card-body">
            <h3>LOVE AND WAR</h3>
            <p class="card-author">Dss</p>
            <div class="card-meta">
              <span class="price">₹5.99</span>
              <button class="btn-add" type="button">Add to cart</button>
            </div>
          </div>
        </article>

      </div>
    </div>
  </section>

  <!-- GENRES -->
  <section class="genres" id="genres">
    <div class="wrap">
      <div class="section-head">
        <h2>Find your shelf</h2>
        <p>Browse by the mood you're in, not just the category.</p>
      </div>
      <div class="genre-row">
        <a href="#shelf" class="genre-tag">Fiction</a>
        <a href="#shelf" class="genre-tag">Mystery &amp; Thriller</a>
        <a href="#shelf" class="genre-tag">Science Fiction</a>
        <a href="#shelf" class="genre-tag">Romance</a>
        <a href="#shelf" class="genre-tag">Poetry</a>
        <a href="#shelf" class="genre-tag">Non-fiction</a>
        <a href="#shelf" class="genre-tag">Essays</a>
        <a href="#shelf" class="genre-tag">Children's</a>
      </div>
    </div>
  </section>

  <!-- QUOTE / ABOUT -->
  <section class="quote-band" id="about">
    <div class="wrap quote-inner">
      <blockquote>
        A book is the only place in which you can examine a fragile thought
        without breaking it.
      </blockquote>
      <p class="quote-attr">&mdash; Divyansh S.Solanki</p>
      <p class="about-copy">bookhub started as a reading list passed between three friends.
      It's still run that way: small batches of titles, chosen carefully, sold without
      the noise of a big storefront. No subscriptions, no algorithms &mdash; just books.</p>
    </div>
  </section>

  <!-- NEWSLETTER -->
  <section class="newsletter" id="newsletter">
    <div class="wrap newsletter-inner">
      <div>
        <h2>Get one good book a month</h2>
        <p>A short note from us, a new recommendation, nothing else in your inbox.</p>
      </div>
      <form class="newsletter-form" action="#" method="post">
        <label for="email" class="sr-only">Email address</label>
        <input type="email" id="email" name="email" placeholder="you@example.com" required>
        <button type="submit" class="btn btn-primary">Subscribe</button>
      </form>
    </div>
  </section>

</main>

<footer class="site-footer">
  <div class="wrap footer-inner">
    <div class="footer-brand">
      <span class="brand">BOOKHUB</span>
      <p>A small e-book store for careful readers.</p>
    </div>
    <div class="footer-col">
      <h4>Shop</h4>
      <a href="#shelf">Featured</a>
      <a href="#genres">Genres</a>
      <a href="#">New releases</a>
    </div>
    <div class="footer-col">
      <h4>BOOKHUB</h4>
      <a href="#about">About</a>
      <a href="#newsletter">Contact</a>
      <a href="#">FAQ</a>
    </div>
    <div class="footer-col">
      <h4>Follow</h4>
      <a href="#">Instagram</a>
      <a href="#">Threads</a>
      <a href="#">RSS</a>
    </div>
  </div>
  <div class="wrap footer-bottom">
    <p>&copy; 2026 BOOKHUD Books. A student mini-project, built with HTML &amp; CSS only.</p>
  </div>
</footer>

</body>
</html>
