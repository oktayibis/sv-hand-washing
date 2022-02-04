<script>
	import HowTo from "./Howto.svelte"
	import Progress from "./Progress.svelte"
	import Timer from "./Timer.svelte"

	// variables
	let title = "Washing Hand Timer"
	let startSecond = 0
	let timer = null
    function incSecond() {
       startSecond++
    }
    function start() {
		if(!timer) { 
			timer = setInterval(incSecond, 1000)
		}

    }

    $: if(startSecond > 19) {
        clearInterval(timer)
    }
</script>

<main>
<div class="container">
	<p class="subtitle color-blue"> {title}</p>
	<Timer second={startSecond} />
	<button disabled={!!timer} on:click={start} class="button"> Start</button>

	<Progress percent={startSecond} />
	<HowTo />
</div>
</main>

<style>
	.color-blue {
		color: blue;
	}
</style>