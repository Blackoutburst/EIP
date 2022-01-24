<script>
    import { onMount } from "svelte";

    let showMobileMenu = false;

    const navItems = [
        { label: "Accueil", href:"index.html" },
        { label: "Article", href: "article.html" },
        { label: "Getting Started", href: "getting_started.html" },
        { label: "Interview", href: "interview.html" },
        { label: "Buzzwords", href: "buzzwords.html" }
  ];

  const handleMobileIconClick = () => (showMobileMenu = !showMobileMenu);

  const mediaQueryHandler = e => {
    // Reset mobile state
    if (!e.matches) {
      showMobileMenu = false;
    }
  };

  onMount(() => {
    const mediaListener = window.matchMedia("(max-width: 767px)");

    mediaListener.addListener(mediaQueryHandler);
  });

</script>

<header>
  <div class="header">
    <div class="img-wrapper">
      <img src="img/logo.png" alt="splash" class="splash">
    </div>
    <h1 class="title-name">Atlas Editor</h1>
  </div>
</header>
<nav>
  <div class="inner">
    <div on:click={handleMobileIconClick} class={`mobile-icon${showMobileMenu ? ' active' : ''}`}>
      <div class="middle-line"></div>
    </div>
    <ul class={`navbar-list${showMobileMenu ? ' mobile' : ''}`}>
      {#each navItems as item}
        <li>
          <a href={item.href}>{item.label}</a>
        </li>
      {/each}
    </ul>
  </div>
</nav>



<body>
  <div class="presentation">
      <p style="margin: 20px;">
          Atlas Editor est un éditeur graphique agnostique, c'est à dire qu'il est capable de s'adapter à tous les moteurs de jeux du marché. <br>
          <br>
          Conçus avec des technologies émargeantes telle que:<br>
          <a href="https://www.rust-lang.org" target="_blank" rel="noopener noreferrer">Rust</a>, <a href="https://tauri.studio/" target="_blank" rel="noopener noreferrer">Tauri</a> et <a href="https://svelte.dev" target="_blank" rel="noopener noreferrer">Svelte</a>, cet éditeur vous simplifiera la vie lors de vos développements de jeux vidéo.<br>
          <br>
          Le tout avec une possibilité de personnalisation complète afin de réellement répondre à vos besoins.<br>
          <br>
      </p>
  </div>
  <div class="team">
    <h2>Notre équipe</h2>
    <div class="mugshots">
      <div class="mugshot">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/Alec_pdp.jpg" alt="Alec photo">
        <a class="hidden-link" href="https://www.linkedin.com/in/alec-ferrari-170575196/" target="_blank" rel="noopener noreferrer">Alec Ferrari</a>
      </div>
      <div class="mugshot">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/paul_low.jpg" alt="Paul photo">
        <a class="hidden-link" href="https://www.linkedin.com/in/paulnarchal/" target="_blank" rel="noopener noreferrer">Paul Narchal</a>
      </div>
      <div class="mugshot">
          <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/florian_pdp.png" alt="Florian photo">
        <a class="hidden-link" href="https://github.com/Blackoutburst/" target="_blank" rel="noopener noreferrer">Florian Chanson</a>
      </div>
      <div class="mugshot">
          <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/Corentin_pdp.jpg" alt="Corentin photo">
        <a class="hidden-link" href="https://www.linkedin.com/in/corentin-petrau-116853197/" target="_blank" rel="noopener noreferrer">Corentin Petrau</a>
      </div>
      <div class="mugshot">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/Lyv_pdp.jpeg" alt="Lyvia photo">
        <a class="hidden-link" href="https://www.linkedin.com/in/lyvia-mallereau-280928154/" target="_blank" rel="noopener noreferrer">Lyvia Mallereau</a>
      </div>
      <div class="mugshot">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/raphael_pdp.jpeg" alt="Raphael photo">
        <a class="hidden-link" href="https://www.linkedin.com/in/rapha%C3%ABl-risser-667852197/" target="_blank" rel="noopener noreferrer">Raphael Risser</a>
      </div>
      <div class="mugshot">
        <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/unamed.jpg" alt="Unamed photo">
        <a class="hidden-link" href="https://www.linkedin.com/in/yann-berger-421b41181/" target="_blank" rel="noopener noreferrer">Yann Berger</a>
      </div>
    </div>
  </div>
</body>

<style>

body {
  background-color: #242d3c;
  height: fit-content;
}

a {
  color: white;
  text-decoration: underline;
}
a:hover {
  color: #ee394b;
}

.hidden-link {
  text-decoration: none;
}

.img-wrapper {
  height: 300px;
  width: 300px;
}

.header {
  width: 100%;
  height: 320px;
  padding: 10px;
  color: #ee394b;
  background-color: #242d3c;
  display: flex;
  flex-direction: row;
}

.title-name {
  margin: auto;
  margin-left: 10%;
  font-size: 90pt;
}

img {
    max-width: 100%;
    max-height: 100%;
    height: auto;
}

nav
{
    background-color: #141922;
    font-family: "Helvetica Neue", "Helvetica", "Arial", sans-serif;
    height: 45px;
}

.mugshots {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.mugshot {
  width: fit-content;
  height: fit-content;
  display: flex;
  flex-direction: column;
  margin: 20px;
}

#background-video {
  width: 100vw;
  height: 100vh;
  object-fit: cover;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  z-index: -1;
}

.inner
{
  max-width: 980px;
  padding-left: 20px;
  padding-right: 20px;
  margin: auto;
  box-sizing: border-box;
  display: flex;
  align-items: center;
  height: 100%;
}

.mobile-icon
{
  width: 25px;
  height: 14px;
  position: relative;
  cursor: pointer;
}

.mobile-icon:after,
.mobile-icon:before,
.middle-line
{
  content: "";
  position: absolute;
  width: 100%;
  height: 2px;
  background-color: #fff;
  transition: all 0.4s;
  transform-origin: center;
}

.mobile-icon:before,
.middle-line
{
  top: 0;
}

.mobile-icon:after,
.middle-line
{
  bottom: 0;
}

.mobile-icon:before
{
  width: 66%;
}

.mobile-icon:after
{
  width: 33%;
}

.middle-line
{
  margin: auto;
}

.mobile-icon:hover:before,
.mobile-icon:hover:after,
.mobile-icon.active:before,
.mobile-icon.active:after,
.mobile-icon.active .middle-line
{
  width: 100%;
}

.mobile-icon.active:before,
.mobile-icon.active:after
{
  top: 50%;
  transform: rotate(-45deg);
}

.mobile-icon.active .middle-line
{
  transform: rotate(45deg);
}

.navbar-list
{
  display: none;
  width: 100%;
  justify-content: space-between;
  margin: 0;
  padding: 0 40px;
}

.navbar-list.mobile
{
  background-color: rgba(0, 0, 0, 0.8);
  position: fixed;
  display: block;
  height: calc(100% - 45px);
  bottom: 0;
  left: 0;
}

.navbar-list li
{
  list-style-type: none;
  position: relative;
}

/* .navbar-list li:before
{
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 1px;
  background-color: #424245;
} */

.navbar-list a
{
  color: #fff;
  text-decoration: none;
  display: flex;
  height: 45px;
  align-items: center;
  padding: 0 10px;
  font-size: 25px;
}

.navbar-list a:hover
{
    color: #ee394b!important;
}

@media only screen and (min-width: 767px)
{
    .mobile-icon
    {
      display: none;
    }

    .navbar-list
    {
      display: flex;
      padding: 0;
    }

    .navbar-list a
    {
      display: inline-flex;
    }
}
.splash
{
    width: 100%;
    padding: 0px;
    margin: 0px;
}

.team
{
    font-size: 1.5vw;
    text-align: center;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 10vh;
    font-weight: bold;
    color: white;
    background-color: #141922CC;
}

.presentation
{
    font-size: 2vw;
    text-align: center;
    padding-top: 10vh;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 10vh;
    color: white;
    background-color: #141922CC;
}
</style>
