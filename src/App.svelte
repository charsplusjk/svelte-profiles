<script lang="ts">
	import Title from "./components/Title.svelte";
</script>

<div class="app">
	<header>
		
		<Title />
	</header>
</div>

<style>
	.app {
    	max-height: 100vh;
	}

	header {    
		display: flex;
		align-items: center;
		justify-content: space-between;
	}

  
</style>