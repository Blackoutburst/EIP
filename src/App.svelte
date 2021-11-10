<script>
    //import { tweened } from 'svelte/motion';
    import Countdown from 'svelte-countdown';
    //import { Typewriter } from "svelte-typewriter";

//     let test = new Date("2021-11-15T17:00:00").getTime();
//     let now = new Date().getTime();
//     let timer = tweened(test-now);

//   // ------ dont need to modify code below
//   setInterval(() => {
//     if ($timer > 0) $timer--;
//   }, 1000);

//   $: days = Math.floor($timer);
//   $: dayname = days > 1 ? " days" : " day";
//   $: hours = Math.floor(($timer - (days*86400))/3600);
//   $: hourname = hours > 1 ? " hours" : " hour";
//   $: minutes = Math.floor(($timer - ((days*86400)+(hours*3600))) / 60);
//   $: minname = minutes > 1 ? " mins" : " min";
//   $: seconds = Math.floor(($timer - ((days*86400) + (hours*3600) + (minutes*60))));

</script>

<main>
  <div class="flex">
    <img src="img/splash.jpg" alt="splash" class="splash">
  </div>

</main>

<body>

    <Countdown from="2021-11-15 17:00:00" format="YYYY-MM-DD H:m:s" zone="Europe/Athens" let:remaining>
        <div class="whatever">
            {#if remaining.done === false}
            <strong>{remaining.days} days</strong>
            <strong>{remaining.hours} hours</strong>
            <strong>{remaining.minutes} minutes</strong>
            <strong>{remaining.seconds} seconds</strong>
            {:else}
            <h2>The time has come!</h2>
            {/if}
        </div>
    </Countdown>

  <!-- <div class="Timer">
    {#if timer < 1}
      <Typewriter loop>
        <h1>Starting soon....</h1>
      </Typewriter>
    {:else}
    <h1>We will be back in <span class="days">{days}</span>{dayname}
        <span class="hours">{hours}</span>{hourname}
        <span class="mins">{minutes}</span>{minname} 

        <span class="secs">{seconds}</span>s!</h1>
    <progress value={$timer/(test-now)}></progress>
      {/if}
  </div> -->
  <!-- 	feel free to modify this text!! -->
    <div class="Name">
      <strong>Next update </strong> 
      : Final WebSite<br>
      <strong>Last Update</strong>
      : Florian Chanson && Corentin Petrau
    </div>
</body>

<style>
    main {
      margin: 0 auto;
    }
    body {
        text-align: center;
    }

    .whatever {
        font-size: 50px;
    }

    .Name {
        font-size: 35px;
    }
    /* progress {
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
    } */
</style>
