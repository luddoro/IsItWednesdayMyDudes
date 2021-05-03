<svelte:head> 
	<title>Isitwednesdaymydudes?</title>
</svelte:head>
<script>

import YoutubeAPI from './YoutubeAPI.svelte';
	
 	let currentDate = new Date();



 </script> 
 



<div class="flex-wrapper">
	<div class="content">
		{#if currentDate.getDay() === 3}
			<img class="frog" src="/wednesdayfrog.png" alt="Wednesdayfroge">
		{:else}
			<h1> Its not Wednesday my dudes :( </h1>
		{/if}	 
	</div> 
	<div class="youtubePlayer">
		<YoutubeAPI></YoutubeAPI>
	</div>
</div>


<style>

.flex-wrapper {
	display: flex;
	flex-flow: row wrap;
	justify-content: center;
	align-items: center;

	min-height: 100vh;
	min-width: 100vw;

	background-color: #dadada;
	color: #333333;
	font-size: 2.5vw;
	font-weight: 10;
	overflow: hidden;
}
.frog {
	width: 100%;
	height: auto;
	max-width: 400px;
}

</style>


