<script lang="ts">
import type IUser from "../interfaces/IUser";


	let inputValue = '';

    export let user: IUser | null;

    async function formSubmit() {
		const userResponse = await fetch(`https://api.github.com/users/${inputValue}`);
		const userData = await userResponse.json();

		user = {
			login: userData.login,
			name: userData.name,
			avatar_url: userData.avatar_url,
			profile_url: userData.profile_url,
			public_repos: userData.public_repos,
			followers: userData.followers
		}
	}
</script>

<form on:submit|preventDefault={formSubmit}>
    <input type="text" class="input" bind:value={inputValue} placeholder="Search user">
    <div class="container-button">
        <button type="submit" class="button">Search</button>
    </div>
</form>

<style>
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
</style>