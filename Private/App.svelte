<script>
    import { onMount } from "svelte";

    let showMobileMenu = false;

    const navItems = [
    { label: "Accueil", href:"#" },
    { label: "Article", href: "article.html" },
    { label: "Getting Started", href: "getting_started.html" },
    { label: "Interview", href: "Interview.Svelte" }
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
        <img src="img/splash.jpg" alt="splash" class="splash">
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
      <video id="background-video" autoplay loop muted>
        <source src="video/CRYSTAL_V3.mp4" type="video/mp4">
      </video>
      <h1>Présentation Crystal Editor</h1>
        <p>
            Crystal Editor est un éditeur graphique agnostique, c'est à dire qu'il est capable de s'adapter à tous les moteurs de jeux du marché. <br>
            <br>
            Conçus avec des technologies émargeantes telle que:<br>
            <a href="https://www.rust-lang.org" target="_blank" rel="noopener noreferrer">Rust</a>, <a href="https://tauri.studio/" target="_blank" rel="noopener noreferrer">Tauri</a> et <a href="https://svelte.dev" target="_blank" rel="noopener noreferrer">Svelte</a>, cet éditeur vous simplifiera la vie lors de vos développements de jeux vidéo.<br>
            <br>
            Le tout avec une possibilité de personnalisation complète afin de réellement répondre à vos besoins.<br>
            <br>
            Ce projet est en relation directe avec le moteur de jeu <a href="https://amethyst.rs" target="_blank" rel="noopener noreferrer">Amethyst</a>
        </p>
    </div>
    <div class="equipe">
      <h2>Notre équipe</h2>
      <div class="teams1">
        <td>
          <!-- svelte-ignore a11y-img-redundant-alt -->
          <img src="img/Alec_pdp.jpg" alt="Alec photo">
          <a href="https://www.linkedin.com/in/alec-ferrari-170575196/" target="_blank" rel="noopener noreferrer"><br>Alec Ferrari&emsp;</a>
        </td>
        <td>
          <!-- svelte-ignore a11y-img-redundant-alt -->
          <img src="img/paul_low.jpg" alt="Paul photo">
          <a href="https://www.linkedin.com/in/paulnarchal/" target="_blank" rel="noopener noreferrer"><br>Paul Narchal&emsp;</a>
        </td>
        <td>
           <!-- svelte-ignore a11y-img-redundant-alt -->
          <img src="img/florian_pdp.png" alt="Florian photo">
          <a href="#" target="_blank" rel="noopener noreferrer"><br>Florian Chanson&emsp;</a>
        </td>
        <td>
           <!-- svelte-ignore a11y-img-redundant-alt -->
          <img src="img/Corentin_pdp.jpg" alt="Corentin photo">
          <a href="https://www.linkedin.com/in/corentin-petrau-116853197/" target="_blank" rel="noopener noreferrer"><br>Corentin Petrau</a>
        </td>
      </div>
      <br><br>
      <div class="teams2">
      <td>
         <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/Lyv_pdp.jpeg" alt="Lyvia photo">
        <a href="https://www.linkedin.com/in/lyvia-mallereau-280928154/" target="_blank" rel="noopener noreferrer"><br>Lyvia Mallereau&emsp;</a>
      </td>
      <td>
         <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/raphael_pdp.jpeg" alt="Raphael photo">
        <a href="https://www.linkedin.com/in/rapha%C3%ABl-risser-667852197/" target="_blank" rel="noopener noreferrer"><br>Raphael Risser&emsp;</a>
      </td>
      <td>
         <!-- svelte-ignore a11y-img-redundant-alt -->
        <img src="img/unamed.jpg" alt="Unamed photo">
        <a href="https://www.linkedin.com/in/yann-berger-421b41181/" target="_blank" rel="noopener noreferrer"><br>Yann Berger</a>
      </td>
      </div>
    </div>
</body>

<style>

nav
{
    background-color: rgba(29, 11, 25, 0.8);
    font-family: "Helvetica Neue", "Helvetica", "Arial", sans-serif;
    height: 45px;
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

.navbar-list li:before
{
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 1px;
  background-color: #424245;
}

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
    color: #007bff!important;
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

.equipe
{
    font-size: 1.5vw;
    text-align: center;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 10vh;
    font-weight: bold;
    color: black;
    background-color: rgba(255, 255, 255, 0.6);
}

.presentation
{
    font-size: 2vw;
    text-align: center;
    padding-top: 10vh;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 10vh;
    color: black;
    background-color: rgba(255, 255, 255, 0.6);
}
</style>
