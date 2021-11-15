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

<body>
<div class="header">
    <img src="img/splash.jpg" alt="splash" class="splash">
</div>

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

<h1 class="title">Crystal Editor : un éditeur pour engine open-source, réalisé par des étudiants.</h1>
<p class="text">
Depuis quelques années de nombreux fondations, entreprises, ou associations, travaillent à promouvoir l’open-source via différent projets.<br><br>
C’est le cas de la fondation Amethyst et de son engine éponyme, développé depuis environ 4 ans. Cet engine open-source fonctionne avec le langage Rust, lui aussi open-source. Il s’agit d’un langage récent, toujours développé par une communauté très active. Bien que le projet bat de l’aile depuis plusieurs mois, les collaborateurs sont toujours présents, même en petit nombre, et continue de faire vivre le projet en contribuant, chacun à manière.<br><br>
C’est au début d’octobre 2021 que le comité de la fondation Amethyst a décidé d’arrêter définitivement le projet malgré l’envie des contributeurs de continuer. Cette décision a été motivé par plusieurs raisons: l’arrêt du développement faute de moyens et de perte importante de contributeurs, la perte du modèle du “Dictateur bénéfique”, etc. Le but de la fondation est de contribuer à l’environnement de GameDev de Rust (un tout nouveau langage et , pour préciser, la plupart des fondateurs d’Amethyst ont créer). L’engine ne contribuait plus à cet écosystème et n’avait donc plus sa place à côté de nouveaux projets, plus récents et avec plus de contributeurs. Le comité a donc décidé de changer de direction.<br><br>
Celle-ci est simple. Si il existe d’autres engines pour Rust, la majorité d’entre eux ne disposent pas des outils nécessaires à une utilisation ergonomique de leurs engine. Un éditeur est un projet conséquent et dur à développer. Le comité a donc eu l’idée de résoudre ce problème grâce à un éditeur qui soit indifférent de l’engine avec lequel il est utilisé. Un éditeur qui fonctionne avec n’importe quel engine si tant est que celui-ci implémente l’interface nécessaire (appellation exacte est éditeur agnostique).<br><br>
Les étudiants ayant déjà prévu de réaliser l’éditeur avant même que le projet principal soit arrêté, ils pourront se concentrer sur ce nouveau projet et travailler en étroite collaboration avec la fondation Amethyst. Ce projet, plus large, peut permettre aux étudiants d’acquérir des compétences tout en travaillant sur un projet open-source mais aussi permettre aux développeurs d’avoir une vue plus “fraîche” sur le projet.<br><br>
En outre, la création de cet éditeur n’a pas seulement pour but de permettre aux étudiants d’acquérir des compétences mais aussi de donner une vraie visibilité à l’open-source. On sait bien que depuis quelques années l’open-source fait grandement parler: les contributeurs à n’importe quel projet sont parfois bien plus avantagés (on peut ici parler d’un des principaux, et fondateur d’Amethyst, qui s’est vu débaucher par Blizzard-Entertainement et à du quitter le projet).<br><br>
Cette visibilité permet aussi aux étudiants, plus jeunes et en début de carrière ou d’études, de voir qu’il n’y a pas seulement le travail en grande entreprise qui compte, mais qu’ils peuvent, au travers de différentes contributions être repérés par de nombreuses entreprises.<br><br>
Il est bien entendu difficile de vendre de l’open-source mais la “promotion” qu’engendre certains projets ne tombent, très souvent, pas dans les méandres d’internet.<br><br>
Pour des projet comme Amethyst et son éditeur, c’est bien avant tout la motivation principal. On peut entendre ici qu’il faut être passionné pour travailler et contribuer à ce genre de projet.<br><br>
Mais n’est-ce pas cela le principal ? Car c’est avant tout la passion qui fait avancer le monde et permet à des jeunes étudiants, et débutant dans ce milieu, de comprendre les mécaniques et aussi de se faire un réseau de professionnels, ou d’amis, dans le meilleur des cas.<br><br>
Si vous souhaitez contribuer à ce projet voici le lien conduisant vers le site d’Amethyst: <a href="https://amethyst.rs" target="_blank" rel="noopener noreferrer">https://amethyst.rs</a><br><br><br>

Retrouvez cet article sur <a href="https://medium.com/@lyvia.mallereau/crystal-editor-un-éditeur-pour-engine-open-source-réalisé-par-des-étudiants-7f9a8497b630" target="_blank" rel="noopener noreferrer">Medium</a>
</p>

</body>

<style>

nav
{
    background-color: rgba(29, 11, 25, 0.8);
    font-family: "Helvetica Neue", "Helvetica", "Arial", sans-serif;
    height: 45px;
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

.splash {
    width: 100%;
    padding: 0px;
    margin: 0px;
}

.title {
    font-size: 3vw;
    text-align: left;
    padding-top: 10vh;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 1vh;
}

.text {
    font-size: 1.4vw;
    text-align: left;
    padding-top: 10vh;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 10vh;
}
</style>
