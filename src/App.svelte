<script lang="ts">
	import SuperiorBar from "./components/SuperiorBar.svelte";
	import Title from "./components/Title.svelte";

	let inputValue = '';

	function formSubmit() {
		console.log(inputValue);
	}
</script>

<div class="app">
	<header>
		<Title />

		<div class="user-search">
			<form on:submit|preventDefault={formSubmit}>
				<input type="text" class="input" bind:value={inputValue}>
				<div class="container-button">
					<button type="submit" class="button">Search</button>
				</div>
			</form>
		</div>
	</header>

	<div class="user">
		<SuperiorBar />

		<div class="user-container">
			<div class="container-photo">
				<a href="" target="_blank" rel="noopener">
					<div class="user-photo"></div>
				</a>
			</div>
		</div>

		<div class="user-details">
			<div class="info">
				Name: <span></span>
			</div>
			<div class="info">
				User: <span></span>
			</div>
			<div class="info">
				Followers: <span></span>
			</div>
			<div class="info">
				Repos: <span></span>
			</div>
		</div>

	</div>
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

	.input {
		padding: 15px 25px;
		width: calc(100% - 8.75rem);
		font-size: 1rem;
		border-radius: 8px;
		border: 1px solid #2e80fa;
		box-shadow: 0px 17px 52px rgba(222, 231, 247, 0.4);
		outline: 0;
	}

	.input::placeholder {
		font-family: "Roboto";
		font-style: italic;
		font-weight: 300;
		font-size: 19.5px;
		line-height: 26px;
		color: #6e8cba;
	}

	.container-button {
		position: absolute;
		width: 9.625rem;
		right: 0;
		top: 0;
		bottom: 0;
		display: flex;
	}

	.button {
		padding: 15px 24px;
		border-radius: 8px;
		border: none;
		background: #2e80fa;
		line-height: 26px;
		color: #fff;
		font-size: 22px;
		cursor: pointer;

		transition: background-color 0.2s;

		display: flex;
		align-items: center;
		gap: 13px;
	}

	.button:hover {
		background: #4590ff;
	}

	.user-card {
		margin-top: 65px;
	}

	.user {
		padding: 28px 0;
		background: rgba(255, 255, 255, 0.5);
		box-shadow: -12px 37px 45px rgba(133, 127, 201, 0.18);
		border-radius: 0px 0px 13px 13px;

		display: flex;
		justify-content: center;
	}

	.container-photo {
		margin-right: 81px;
	}

	.user-photo {
		width: 12.75rem;
		height: 12.75rem;
		border: 4.56px solid #2e80fa;
		border-radius: 50%;
		background-size: cover;
	}

	.user-details {
		margin-right: 55px;
	}

	.user-details > .info {
		font-weight: 600;
		font-size: 20px;
		line-height: 31px;
		color: #395278;
	}

	.user-details > .info > span {
		color: #6781a8;
		font-weight: normal;
	}
</style>