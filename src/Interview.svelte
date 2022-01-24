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
  <header>
    <div class="header">
      <div class="img-wrapper logo">
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

<h1 class="title">Interview d'un utilisateur</h1>
<p class="text">
- Première question, savez-vous ce qu'est la différence entre un éditeur et un game
engine ?<br><br>
- Alors j'ai découvert la différence avec votre explication lors de votre présentation des
warm-Up day.<br><br>
- Très bien, et du coup qu'avez vous pensé du pitch ?<br><br>
- Le pitch était très clair, compréhensible et intuitif que j'ai bien compris ce qu'il en
retourné.<br><br>
- Du coup, que pensez-vous du Crystal Editor ?<br><br>
- Je pense que c'est un projet qui peut avoir de l'avenir, ce que j'entend par là c'est
qu'en réalité le projet est très bien mais si la communauté d'amethyst ne vous
soutient plus il est probable que votre projet s'effondre. Il faut vraiment que vos
bases soient solides pour un projet d'une telle envergure.<br><br>
- Comment ça, le projet s'effondre ?<br><br>
- Je pense que si la fondation amethyst ne vous supporte plus il est possible que votre
projet devienne un calvaire de travail pour vous. Ne mettez pas tous vos œufs dans
le même panier et renseignez vous bien sur les communautés qui pourraient vous
soutenir.<br><br>
- D'accord, merci du conseil ! Pensez-vous utiliser le Crystal Editor plutôt que Unity
(par exemple) ?<br><br>
- Celà pourrait m'apporter de nouvelles compétences du fait de devoir utiliser un
engine “Maison” plutôt qu'un incontournable comme Unity. De plus, je comprendrai
beaucoup mieux comment fonctionne mon jeu car rien ne serait "caché" par l'engine.<br><br>
- Vous vous dirigez donc plus vers une utilisation de Crystal pour des projets
personnels ou professionnels ?<br><br>
- Plutôt pour des projets personnels, pour le professionnels je préfère rester sur un
éditeur qui “a fait ses preuves” néanmoins si votre éditeur nous prouve sur ces 3 ans
sa fiabilité et son agnosticité alors je pourrai réfléchir à en avoir une utilisation plus
professionnelle.<br><br>
- Recommanderiez-vous notre projet à des débutants ou des personnes novices dans
le jeu vidéo ?<br><br>
- Non, votre projet actuel demande déjà une connaissance assez poussée du
fonctionnement d'un engine et de ce qu'il en retourne. Par ailleurs, si vous
réussissez à proposer une interface simple de prise en main et assez visuel pour que
même un débutant comprenne facilement ce qu'il fait, alors la vous aurez réussi à
toucher une nouvelle cible pour votre projet.<br><br>
- D'accord, avez-vous encore des suggestions sur ce que nous pourrions améliorer ?<br><br>
- En réalité, vous avez déjà l'air de faire pas mal sur votre projet, le site en<br><br>
construction, les posts LinkdIn, la communication sur les différents discord/blog. Et je
sais que comme vous êtes un projet Open Source, peu de personnes croient en la
viabilité de votre projet du au faite que vous ne fassiez pas d'argent. mais sachez
que l'argent ne fait pas tout même s'il est moteur de beaucoup de chose à la fin vous
aurez les mêmes compétences que quelqu'un qui à gagné 100€ avec son EIP.<br><br>
- Merci pour tous vos conseils et merci pour votre temps.<br><br>
- Pas de souci, j'ai toujours du temps pour aider les jeunes.<br><br>
</p>


<h1 class="title">INTERVIEW AVEC UNE ALUMNI</h1>
<p class="text">
Corentin : Peux-tu te présenter ?<br><br>
Héloïse : Je m'appelle Héloïse de Villepin, je suis de la promo 2020 et je suis depuis 2 ans
employée à Epitech, d'abord comme cheffe de projet du Coding Club puis comme
responsable du module Epitech Diversity.<br><br>
C : Au sein de ce projet nous nous sommes répartis en 2 groupes, Florian et moi-même qui
travaillons sur la partie “Front” du projet et le reste sur la partie “Back”, penses tu que c'est
une bonne chose ?<br><br>
H : Pour des raisons d'organisation, il est important de séparer le travail technique en
plusieurs parties comme vous l'avez fait mais pensez également à désigner plusieurs “têtes
pensantes” pour vous occuper de la partie administrative et de la vision du projet. La totalité
des membres ne touchera jamais à la rédaction de documents ou n'aura jamais
spécialement d'intérêt pour imaginer les prochaines features donc choisissez ensemble les
personnes qui s'en occupent d'office. Pour tout ce qui est graphique/marketing, il est
également intéressant de désigner 2 personnes si vous êtes assez nombreux, de préférence
ceux qui ont le plus de créativité et de feeling avec l'aspect publicitaire et design. Ces deux
parties devront accorder de l'importance à l'UX car votre produit doit être ergonomique pour
votre utilisateur, donc il faut chercher leur avis et vous en servir pour améliorer vos
fonctionnalités.<br><br>
C : En ce qui concerne notre temps d'implication dans le projet, étant donné que nous
sommes sept et qu'il nous faut travailler sur l'EIP au moins une journée, nous nous sommes
placés chacun sur un jour de la semaine, penses-tu que c'est une bonne chose ?<br><br>
H : La meilleure façon de fonctionner est celle qui vous correspond. Dans mon EIP, il était
régulier que nous travaillions soit en binôme soit en solo, selon les besoins. Je vous
conseille de rester souples et de vous adapter quand vos plannings et votre nécessité à
collaborer sur des features le requièrent.<br><br>
C : L'un des problèmes de notre EIP est qu'il est en collaboration avec la fondation
Amethyst, par conséquent, on hésite par moment à faire quelque chose sans attendre leur
avis, est-ce une bonne chose ?<br><br>
H : En avançant sans eux, finalement est-ce que vous collaborez ensemble ? Quand vous
faites face à des difficultés de communication, il vaut mieux provoquer une rencontre (appel
en visio, petite réunion en physique, etc) afin de vous mettre sur la même longueur d'ondes.
Peut-être que la fondation acceptera que vous avanciez sans eux tout en les tenant au
courant des progrès effectués, ou peut-être qu'ils se mettront à s'investir davantage dans
votre partenariat. Dans tous les cas, pensez à les informer clairement de vos besoins et de
vos attentes sur leurs actions et demandez-leur quels sont les leurs. Ça peut être vraiment
utile pour la suite.

</p>

</body>

<style>

body {
  background-color: #242d3c;
  height: fit-content;
  color: white;
}

a {
  color: white;
  text-decoration: underline;
}
a:hover {
  color: #ee394b;
}

.logo {
  margin-top: auto;
  margin-bottom: auto;
  position: absolute;
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
