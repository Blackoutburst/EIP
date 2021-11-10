<script>
    import { tweened } from 'svelte/motion';
    //import { Typewriter } from "svelte-typewriter";

    let original = 8640 * 60; // TYPE NUMBER OF SECONDS HERE
    let timer = tweened(original)

  // ------ dont need to modify code below
  setInterval(() => {
    if ($timer > 0) $timer--;
  }, 1000);

  $: days = Math.floor($timer/86400);
  $: dayname = days > 1 ? " days" : " day";
  $: hours = Math.floor(($timer - (days*86400))/3600);
  $: hourname = hours > 1 ? " hours" : " hour";
  $: minutes = Math.floor(($timer - ((days*86400)+(hours*3600))) / 60);
  $: minname = minutes > 1 ? " mins" : " min";
  $: seconds = Math.floor(($timer - ((days*86400) + (hours*3600) + (minutes*60))));
</script>

<main>
  <div class="flex">
    <img src="img/splash.jpg" alt="splash" class="splash">
  </div>

</main>

<body>

  <div class="Timer">
    {#if timer < 1}
      <!-- <Typewriter loop>
        <h1>Starting soon....</h1>
      </Typewriter> -->
    {:else}
    <h1>We will be back in <span class="days">{days}</span>{dayname}
        <span class="hours">{hours}</span>{hourname}
        <span class="mins">{minutes}</span>{minname} 

        <span class="secs">{seconds}</span>s!</h1>
    <progress value={$timer/original}></progress>
      {/if}
  </div>
  <!-- 	feel free to modify this text!! -->
    <strong>Next update </strong> 
    : Final WebSite<br>
    <strong>Last Update</strong>
    : Florian Chanson && Corentin Petrau
</body>

<style>
    main {
      margin: 0 auto;
    }
    body {
        text-align: center;
    }

    progress {
        width: 600px;
    }
    .days {
        color: darkgoldenrod;
    }
    .hours {
        color: darkgoldenrod;
    }
    .mins {
        color: darkgoldenrod;
    }
    .secs {
        color: darkgoldenrod;
    }
</style>
