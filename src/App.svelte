<script>
	import { onMount } from 'svelte';
	
 	let currentDate = new Date();

// 	onMount(async () => {
// 		const res = await fetch(`https://i.kym-cdn.com/entries/icons/original/000/020/016/wednesdaymydudeswide.jpg`);
// 	 	frog = await res.json();
// })


 </script> 
 



<div class="container">
	<div class="content">
		{#if currentDate.getDay() === 3}
			<img src="/wednesdayfrog.png" alt="Wednesdayfroge">
		{:else}
			<h1> Its not my Wednesday my dudes :( </h1>
		{/if}	 
	</div> 
</div>


<style>
	.container {
		
		display: flex;
		justify-content: center;
		align-items: center;
		height: 100vh;
		width: 100vw;
		margin: 0;
		background-color: #dadada;
	}
	h1 {
		color: #201f1f;
		text-transform: uppercase;
		font-size: 5em;
		font-weight: 150;
	}
	/* main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	



	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	} */
</style>


