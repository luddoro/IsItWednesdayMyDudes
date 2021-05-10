<script>
    import { onMount } from 'svelte';
    
    let deadline = '13 May 2021';
    console.info(deadline);

    function getTimeRemainingOfCountdown (endtime) {

          let total = Date.parse(endtime) - Date.parse(new Date());
          let seconds = Math.floor( (total/1000) % 60 );
          let minutes = Math.floor( (total/1000/60) % 60 );
          let hours = Math.floor( (total/(1000*60*60)) % 24 );
          let days = Math.floor( total/(1000*60*60*24) );

          return {
            total,
            days,
            hours,
            minutes,
            seconds
          };
        }

    let timeLeft = getTimeRemainingOfCountdown(deadline);
    
    onMount( () => {
      const interval = setInterval(() => {
        timeLeft = getTimeRemainingOfCountdown(deadline);
      }, 1000);
    });
   </script>
   <div> 
    {timeLeft.days} : {timeLeft.hours} : {timeLeft.minutes} : {timeLeft.seconds}


   </div>
