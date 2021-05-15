<script lang="typescript">
    import { onMount } from 'svelte';

    
    let today = new Date('2021-05-15T03:24:00');
    let timeLeft;
    const theDay = 3;
    
    if(!todayIsTheDayMyDudes(today)) {
      var nextWedneday = new Date();
      let diff = nextWedneday.getDate() + (theDay - nextWedneday.getDay())%7;
      if (diff < 0){
        nextWedneday.setDate(nextWedneday.getDate() + (theDay - nextWedneday.getDay())%7 + 7);
      }else{
        nextWedneday.setDate(nextWedneday.getDate() + (theDay - nextWedneday.getDay())%7);
      }
      nextWedneday.setHours(0,0,0,0);
      console.log(nextWedneday)

      timeLeft = getTimeRemainingOfCountdown(nextWedneday);
      onMount( () => {
        const interval = setInterval(() => {
          timeLeft = getTimeRemainingOfCountdown(nextWedneday);
        }, 1000);
      });
    }

    function todayIsTheDayMyDudes(today){
      return today.getDay() === theDay ? true : false;
    }

    function getTimeRemainingOfCountdown (endtime) {
      let total = Date.parse(endtime) - new Date('2021-05-16T03:24:00');
      let seconds = Math.floor( (total/1000) % 60 );
      let minutes = Math.floor( (total/1000/60) % 60 );
      let hours = Math.floor( (total/(1000*60*60)) % 24 );
      let days = Math.floor( total/(1000*60*60*24) );

      return {
        days,
        hours,
        minutes,
        seconds
      };
    }
   </script>
   <div style="text-align: center"> 
    {timeLeft.days} : {timeLeft.hours} : {timeLeft.minutes} : {timeLeft.seconds}


   </div>
