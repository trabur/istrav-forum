<script>
  import { onMount } from "svelte";
	import * as animateScroll from "svelte-scrollto"

	import Solutions from '../components/Solutions.svelte'
	import Nav from '../components/Nav.svelte'

	let show = false

	onMount(() => {
		/* particlesJS.load(@dom-id, @path-json, @callback (optional)); */
		particlesJS.load('particles-js', './particles.json', function() {
			console.log('callback - particles.js config loaded');
		});
	})

	function showMagic () {
		show = true
	}
	function hideMagic () {
		show = false
	}
</script>

<svelte:head>
	<title>AAGHC: Kitting & assembly.</title>
</svelte:head>

<div class="masonry">
	<div id="particles-js">
		<div class="middle">
			<div class="logo" on:mouseenter={showMagic} on:mouseleave={hideMagic}>
				{#if show}
					AAGHC
				{:else}
					<div class="first-a">A</div><div class="second-a">A</div><div class="third-g">G</div><div class="rotate-letter">H</div><div class="space-letter">C</div>
				{/if}
			</div>
			<h1 class="slogan">Kitting & assembly.</h1>
			<div class="expand">
				<a href="/#" class="btn-floating btn-large waves-effect waves-light" on:click={() => animateScroll.scrollTo({element: '#platform'})}>
					<i class="material-icons">expand_more</i>
				</a>
			</div>
		</div>
	</div>
</div>
<Nav />
<div id="platform">
	<Solutions />
</div>
<div class="dotted">
	<div style="min-height: 100vh;"></div>
</div>


<style>
	.masonry {
		min-height: 100vh;
		position: relative;
	}

	.middle {
    width: 100%;
    position: absolute;
    top: 50%;
    -ms-transform: translateY(-50%);
    transform: translateY(-50%);
	}

	.logo {
		margin: 0 auto;
		font-size: 5em;
		font-weight: 800;
		text-align: center;
		font-family: sans-serif;
		color: #333;
		cursor: pointer;
		display: table;
	}

	.logo .first-a {
		float: left;
	}

	.logo .second-a {
		margin-left: -0.2em;
		float: left;
	}

	.logo .third-g {
		margin-right: 0.1em;
		float: left;
	}

	.logo .rotate-letter {
		transform: rotate(-90deg);
		float: left;
	}

	.logo .space-letter {
		float: left;
	}

	.slogan {
		font-weight: 600;
		text-align: center;
		margin-top: -0.5em;
    font-size: 2.5em;
		color: #333;
	}

	#platform {
		background-color: #333;
	}

	#particles-js {
		background-color: #ee6e73;
		overflow: hidden;
		position: absolute;
		top: 0;
		right: 0;
		bottom: 0;
		left: 0;
	}

	.expand {
		text-align: center;
	}

	.dotted {
		background-image: radial-gradient(#ddd 20%, transparent 20%), radial-gradient(#ddd 20%, transparent 20%);
    background-color: #eee;
    background-position: 0 0, 50px 50px;
    background-size: 100px 100px;
	}
</style>