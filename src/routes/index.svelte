<script lang="ts">
	import { loginWithGoogle, logout, user } from '../firebase';
	import Profile from '../Profile.svelte';
	import Todos from '../Todos.svelte';
</script>

<section>
	<!-- Interface if user is logged in  -->
	{#if $user}
		<Profile displayName={$user.displayName} photoURL={$user.photoURL} uid={$user.uid} />
		<button on:click={logout}>Logout</button>
		<hr />
		<Todos uid={$user.uid} />
	<!-- Interface if user is logged out -->
	{:else}
		<button on:click={loginWithGoogle}>Signin with Google</button>
	{/if}
</section>
