<script>
	let authenticated = false;

	import { link } from "svelte-routing";
  	import Newsfeed from "@/routes/Newsfeed.svelte";

	if ('token' in localStorage) {
		authenticated = true;
	}
</script>

{#if authenticated}
	<Newsfeed />
{:else}
<section class="section">
  <div class="hero fullscreen">
    <div class="hero-body">
      <div class="content">
        <div class="text-center">
          <h1>🙏 नमस्ते world! 👋</h1>
          <h4 class="font-alt font-light">You may <a href="/auth" use:link>login</a> if you wish to continue.</h4>
          <hr>
          <h6 class="font-alt font-light">A web application powered by <b><a target="_blank" href="https://git.io/vulnfapi">vFastAPI!</a></b></h6>
        </div>
      </div>
    </div>
  </div>
</section>
{/if}

<style>
  .section {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    .section {
      max-width: none;
    }
  }
</style>
