<svelte:head> 
	<title>Isitwednesdaymydudes?</title>
</svelte:head>
<script>
	import Timer from "./Timer.svelte"
 	let currentDate = new Date();

 </script> 

<div class="flex-wrapper">
	<div class="content">
		{#if currentDate.getDay() === 3}
			<div id="frog-img">
				<img class="frog" src="/wednesdayfrog.png" alt="Wednesdayfroge">
			</div>
			<div id="player"></div>
			<script>
				var tag = document.createElement('script');

				tag.src = "https://www.youtube.com/iframe_api";
				var firstScriptTag = document.getElementsByTagName('script')[0];
				firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

				var now = new Date();
				var start = new Date(now.getFullYear(), 0, 0);
				var diff = (now - start) + ((start.getTimezoneOffset() - now.getTimezoneOffset()) * 60 * 1000);
				var oneDay = 1000 * 60 * 60 * 24;
				var day = Math.floor(diff / oneDay);

	
			index = Math.floor((day % 53) + 1);
			var player;
			function onYouTubeIframeAPIReady() {
				player = new YT.Player('player', {
					height: '390',
					width: '640',
					playerVars: {
								listType:'playlist',
								list:'PLy3-VH7qrUZ5IVq_lISnoccVIYZCMvi-8',
								index: index,
					},
					events: {
						'onReady': function (event) {
					
							event.target.playVideo();
							setTimeout(function() {
								event.target.setShuffle({'shufflePlaylist' : true});
							}, 1000);
						}
					}
				});
			}
			</script>
		{:else}
			<h1> Its not Wednesday my dudes :( </h1>
			<Timer></Timer>
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
	font-size: 2.5vw;
	font-weight: 10;
	overflow: hidden;
}

.frog {
	width: 100%;
	height: auto;
	max-width: 400px;
}

#player {
	max-width: 100%
}

#frog-img {
	width: 100%; 
	text-align: center;
}
</style>