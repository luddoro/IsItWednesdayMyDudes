<script>
	import { onMount } from 'svelte';
	
 	let currentDate = new Date();



 </script> 
 



<div class="flex-wrapper">
	<div class="content">
		{#if currentDate.getDay() === 3}
			<img class="frog" src="/wednesdayfrog.png" alt="Wednesdayfroge">
		{:else}
			<h1> Its not my Wednesday my dudes :( </h1>
		{/if}	 
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
	font-size: 3em;
	font-weight: 150;
	overflow: hidden;
}
.content {
	
}
.frog {
	width: 100%;
	height: auto;
	max-width: 400px;
}

</style>


