<!-- <h1>Welcome to your library project</h1>
<p>Create your package using @sveltejs/package and preview/showcase your work with SvelteKit</p>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p> -->
<script lang="ts">
	import { onMount } from 'svelte';
	import { goto } from '$app/navigation';
	import logo from '$lib/assets/images/neb-logo.svg';
	import logo_header from '$lib/assets/images/neb-logo-header.svg';
</script>

<div class="landing-cont">
	<!-- <h1>nebula</h1> -->
	<!-- <img src={logo} alt="" /> -->
	<div class="blurb">
        Over time the inhabitants had become accustomed to a lack of activity. <br />
		The sameness of the days, the seasons, the years. <br />
		Some accepted it, some if they dared to admit it, found comfort in the nothingness. <br />
		The nothingness that was their life. <br />
		And the slow fading away was acceptable, even welcome. <br /> <br/>
        
        There were others, however, who found the nothingness unbearable. <br />
        Who found the nothingness to be a prison. <br />
        Who yearned for something more. <br /> <br/>
        
        And so they left. <br />
	</div>
    
    <div class="leaving-date">
        SCOUTING EXPEDITION : 2023 - 2 - 9 <br />
    </div>

    <div class="logo-container">
        <img id="logo-header" src={logo_header} alt="" />
    </div>
</div>

<style>
    .leaving-date {
        font-family: courier;
        font-size: 1.1rem;
        font-weight: 900;
        color: #fff;
        text-align: Left;
        margin-top: 2rem;
        line-height: 2;
    }

    .blurb {
        /* align-self: center; */
        /* justify-self: center; */
        margin-top: 20%;
        font-size: 1.3rem;
        font-weight: 400;
        color: #fff;
        text-align: left;
        /* margin-top: 2rem; */
        line-height: 2;
    }

	#logo-header {
		width: 100%;
		max-width: 200px;
		height: auto;
	}

    .logo-container {
        margin-top: auto;
        margin-bottom: 2rem;
    }
	.landing-cont {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100vh;
		width: 100vw;
		color: #fff;
		z-index: 1;
		/* background-color: #f5f5f5; */
	}
	h1 {
		font-size: 5rem;
		font-weight: 700;
		color: #fff;
	}
</style>
