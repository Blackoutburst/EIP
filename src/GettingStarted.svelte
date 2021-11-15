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

<h1 id="installing-tauri-on-ubuntu-20-04">Installing tauri on Ubuntu 20.04</h1>
<h2 id="dependencies">Dependencies</h2>
<p>Tauri needs quite a few dependencies to work, add them using this command:</p>
<pre><code class="lang-bash">sudo apt update &amp;&amp; sudo apt install libwebkit2gtk-<span class="hljs-number">4.0</span>-dev <span class="hljs-string">\</span>
    build-essential <span class="hljs-string">\</span>
    curl <span class="hljs-string">\</span>
    wget <span class="hljs-string">\</span>
    libssl-dev <span class="hljs-string">\</span>
    libgtk-<span class="hljs-number">3</span>-dev <span class="hljs-string">\</span>
    libappindicator3-dev <span class="hljs-string">\</span>
    patchelf <span class="hljs-string">\</span>
    librsvg2-dev
</code></pre>
<h2 id="node-js-and-node-version-manager">Node.js and Node Version Manager</h2>
<p>You then need nvm, the Node Version Manager to handle Node.js.<br>Install it using this command:</p>
<pre><code class="lang-bash">curl -<span class="hljs-keyword">o</span>- http<span class="hljs-variable">s:</span>//raw.githubusercontent.<span class="hljs-keyword">com</span>/nvm-<span class="hljs-keyword">sh</span>/nvm/v0.<span class="hljs-number">35.2</span>/install.<span class="hljs-keyword">sh</span> | bash
</code></pre>
<p>You most likely won&#39;t have nvm installed by now.<br>Try using the <code>nvm --version</code> command.<br>If it prints the version of nvm you are currently on, congratulations, you have nvm installed.<br>If instead, you get a <code>command not found: nvm</code> error, this means you need to add nvm to your path.<br>One of the solutions is to add the following line to your .bashrc/.zshrc file (according to the shell you&#39;re using):</p>
<pre><code class="lang-bash"><span class="hljs-keyword">source</span> ~<span class="hljs-regexp">/.nvm/</span>nvm.sh
</code></pre>
<p>Once you reload your terminal, it will be run and you&#39;ll have access to <code>nvm</code>.<br>If you can&#39;t or don&#39;t want to reload the terminal, just launch the <code>source</code> command from before in your terminal.</p>
<h2 id="rust-rustc-and-rustup">Rust, RustC and RustUp</h2>
<p>Tauri recommends using the following line to install rust, however, you can install it another way if you want to.<br>It should work, however, if it doesn&#39;t, you should resort to this command.</p>
<pre><code class="lang-bash">curl --proto <span class="hljs-string">'=https'</span> --tlsv1.<span class="hljs-number">2</span> -sSf http<span class="hljs-variable">s:</span>//<span class="hljs-keyword">sh</span>.rustup.rs | <span class="hljs-keyword">sh</span>
</code></pre>
<p>To test out whether your install works, just type this in your terminal:</p>
<pre><code class="lang-bash">rustc <span class="hljs-comment">--version</span>
</code></pre>
<h2 id="creating-a-tauri-app">Creating a Tauri app</h2>
<p>Tauri devs recommend yarn instead of npm so here is how you create an app:</p>
<pre><code class="lang-bash"><span class="hljs-attribute">yarn create tauri-app</span>
</code></pre>
<p>You&#39;ll be prompted for a lot of minor information. Configure your project how you want and it will generate a simple &quot;hello-world&quot; example app.<br>To use and test your app, you&#39;ll need to compile. Brace yourself, compilation times are quite lengthy to say the least.<br>The first time should last several minutes and subsequent builds most likely will take around 30 secs or less.<br>To build and test, run the following command:</p>
<pre><code class="lang-bash"><span class="hljs-attribute">yarn tauri dev</span>
</code></pre>
<p>You&#39;re good to go, you should follow the few tutorials on Tauri available on the internet and join the Discord community to get started.<br><br><br><br></p>

</body>

<style>

h1 {
    font-size: 3vw;
    text-align: left;
    padding-top: 10vh;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 1vh;
}

h2 {
    font-size: 2vw;
    text-align: left;
    padding-top: 10vh;
    margin-left: 25vw;
    margin-right: 25vw;
    padding-bottom: 1vh;
}

p {
    font-size: 1.4vw;
    text-align: left;
    margin-left: 25vw;
    margin-right: 25vw;
}

pre {
    font-size: 1vw;
    text-align: left;
    margin-left: 25vw;
    margin-right: 25vw;
}

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
</style>
