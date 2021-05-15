<script lang="typescript">
    import { onMount } from 'svelte';
    import nextWednesday from 'date-fns/nextWednesday'

    let today = new Date().setHours(0,0,0,0);
    let deadline = Date.parse(nextWednesday(today).toISOString());

    function getTimeRemainingOfCountdown (deadline) {
      let now = Date.parse(new Date().toISOString());
      let total = deadline - now;
      let seconds = Math.floor( (total/1000) % 60 );
      let minutes = Math.floor( (total/1000/60) % 60 );
      let hours = Math.floor( (total/(1000*60*60)) % 24 );
      let days = Math.floor( total/(1000*60*60*24));
      
      return {
        days,
        hours,
        minutes,
        seconds
      };
    }

    function parseNumber(number){
      if(number < 10){
        return "0"+number;
      }
      return number;
    }

    let timeLeft = getTimeRemainingOfCountdown(deadline);

     onMount( () => {
        const interval = setInterval(() => {
          timeLeft = getTimeRemainingOfCountdown(deadline);
        }, 1000);
      });
   </script>

   <div style="text-align: center"> 
    <h2 style="font-size: 1em"> Time Left: {timeLeft.days} : {parseNumber(timeLeft.hours)} : {parseNumber(timeLeft.minutes)} : {parseNumber(timeLeft.seconds)} </h2>


   </div>
