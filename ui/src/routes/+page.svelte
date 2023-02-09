<script lang="ts">
	import { goto } from '$app/navigation';
	import logo_header from '$lib/assets/images/neb-logo-header.svg';
	import portal_lofi from '$lib/assets/images/portal-8bit.png';
	import Particles from '$lib/components/particles.svelte';
	import { fade } from 'svelte/transition';

	let screen_width: number;
	let story_step = 1;
</script>

{#if story_step === 1}
	<div in:fade={{ duration: 2000 }}>
		<div class="landing-cont">
			<div class="logo-container mt-10">
				<img id="logo-header" src={logo_header} alt="" />
			</div>
			˜
			<div class="leaving-date mt-5 mb-5">
				EVAC POD SIGNAL [ 2023.2.03 ] <br />
			</div>
			<div class="blurb">
				Over time the inhabitants had become accustomed to a lack of activity. <br />
				The sameness of the days, the seasons, the years. <br />
				Some accepted it, some if they dared to admit it, found comfort in the nothingness. <br />
				The nothingness that was their life. <br />
				And the slow fading away was acceptable, even welcome. <br /> <br />

				There were others, however, who found the nothingness unbearable. <br />
				Who found the nothingness to be a prison. <br />
				Who yearned for something more. <br /> <br />

				And so we left. <br />
			</div>

			<div class="mt-8 mb-20">
				<button on:click={() => story_step++} class="next-button gold">
					{'<< Scan for signals >>'}
				</button>
			</div>
		</div>
		<Particles
			bg_color={'#000'}
			particles_color={'#751B59'}
			{screen_width}
			triangles={false}
			distance={40}
			particles_number={[20, 50]}
		/>
	</div>
{:else if story_step === 2}
	<div in:fade={{ duration: 2000 }}>
		<div class="landing-cont pt-10">
			<div class="logo-container" />
			<div class="leaving-date mt-5 mb-5">
				EVAC POD SIGNAL [ 2023.2.10 ] <br />
			</div>
			<div class="blurb">
				Venturing into the depths of space, we sought for something greater. <br /> <br />
				We set course for the source of a mysterious signal, a mere 7 days away.<br /> <br />
				When we arrived at the coordinates, we found the signal to be coming from a solitary asteroid,
				floating endlessly in the void<br /> <br />
			</div>

			<div class="button-container mt-8 mb-20 flex flex-col h-32">
				<button on:click={() => story_step++} class="next-button">
					{'<< explore the asteroid >>'}
				</button>
				<button on:click={() => story_step--} class="next-button btn-small btn-outline">
					{'go back'}
				</button>
			</div>
		</div>
		<Particles
			bg_color={'#000'}
			particles_color={'#fff'}
			{screen_width}
			triangles={false}
			distance={100}
			particles_number={[20, 50]}
		/>
	</div>
{:else if story_step === 3}
	<div in:fade={{ duration: 2000 }}>
		<div class="landing-cont">
			<div class="logo-container" />
			<div class="leaving-date mt-5 mb-5">
				... SIGNAL CONTINUES [ 2023.2.10 ] <br />
			</div>
			<div class="blurb">
				We deployed a party to investigate the asteroid, and there we discovered what appeared to be
				a portal to another world.<br /> <br />
				<div class="portal-img-container">
					<img src={portal_lofi} alt="" />
				</div>

				We stood at the threshold, torn between our thirst for adventure and the fear of the
				unknown.<br />
				We stepped through.<br /> <br />

				Do you dare to follow us?<br />
			</div>

			<div class="button-container flex flex-col mt-4">
				<button
					on:click={() => goto(`https://rocketswap.exchange`)}
					class="next-button btn-primary"
				>
					{'<< enter the portal >>'}
				</button>
				<button on:click={() => story_step--} class="next-button btn-small btn-outline btn-primary">
					{'go back'}
				</button>
			</div>
		</div>
		<Particles
			bg_color={'#000'}
			particles_color={'#ECB75C'}
			{screen_width}
			triangles={false}
			distance={50}
			particles_number={[30, 100]}
		/>
	</div>
{/if}
<svelte:window bind:innerWidth={screen_width} />

<style>
	.portal-img-container {
		height: 300px;
		text-align: center;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}

	.portal-img-container img {
		width: 300px;
	}

	.button-container {
		min-height: 150px;
		justify-content: space-evenly;
		align-items: center;
	}

	button {
		-webkit-box-sizing: border-box; /* Safari/Chrome, other WebKit */
		-moz-box-sizing: border-box; /* Firefox, other Gecko */
		box-sizing: border-box; /* Opera/IE 8+ */
	}

	.btn-primary {
		background-color: #ecb75c !important;
		outline: 1px solid #f6cd62 !important;
		color: #29183f;
	}

	.btn-primary:active {
		outline: 3px solid #f6cd62 !important;
	}

	.btn-small {
		padding: 0.5rem 1rem !important;
		max-width: 300px;
		/* font-size: 1rem !important; */
		font-size: 0.8rem !important;
		font-weight: 600 !important;
	}

	.btn-outline {
		background-color: rgba(0, 0, 0, 0) !important;
	}

	.next-button {
		user-select: none;
		background-color: #751b59;
		outline: 3px solid #a6277e;
		color: #fff;
		padding: 1rem 2rem;
		font-size: 1.2rem;
		font-weight: 700;
		font-family: poppins;
		border-radius: 5px;
		cursor: pointer;
		text-transform: uppercase;
		letter-spacing: 0.15rem;
	}

	.next-button:hover {
		padding: 1rem 2rem;
		font-size: 1.2rem;
		cursor: pointer;
	}

	.next-button:active {
		background-color: #751b59;
		padding: 1rem 2rem;
		font-size: 1.2rem;
		border-radius: 5px;
		cursor: pointer;
		outline: 3px solid #a6277e;
	}

	:global(.leaving-date) {
		font-family: courier;
		font-size: 1.1rem;
		font-weight: 900;
		color: #fff;
		text-align: right;
		line-height: 2;
	}

	:global(.blurb) {
		font-family: poppins;
		padding: 0 2rem;
		font-size: 1.2rem !important;
		font-weight: 200;
		color: #fff;
		text-align: left;
		line-height: 2;
		max-width: 740px;
	}

	#logo-header {
		width: 100%;
		max-width: 200px;
		height: auto;
		margin-bottom: 2rem;
	}

	.logo-container {
		text-align: center;
	}

	.landing-cont {
		display: flex;
		flex-direction: column;
		align-items: center;
		height: 100vh;
		width: 100vw;
		color: #fff;
		z-index: 1;
	}

	@media (min-width: 900px) {
		.landing-cont {
			padding-top: 7%;
		}
		.blurb {
			font-size: 1rem;
		}
	}

	@media (max-width: 600px) {
		.blurb {
			font-size: 1rem;
		}
	}
</style>
