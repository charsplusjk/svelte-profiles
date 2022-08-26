<script lang="ts">
	
	import Form from "./components/Form.svelte";
	import Title from "./components/Title.svelte";
	import User from "./components/User.svelte";
	import type IUser from "./interfaces/IUser";

	let user: IUser | null = null;
</script>

<div class="app">
	<header>
		<Title />

		<div class="user-search">
			<Form bind:user={user}/>
		</div>
	</header>

	{#if user}
		<User user={user} />
	{/if}
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

	.user-search {
		position: relative;
		width: 70%;
	}



	
</style>