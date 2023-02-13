<script>
	import { page } from '$app/stores';
	import './styles.css';
</script>

<!-- Navbar og style til dels hentet fra Sveltes eksempel-app -->
<header>
	<nav>
		<ul>
			<li aria-current={$page.url.pathname === '/' ? 'page' : undefined}>
				<a href="/">Hovedsiden</a>
			</li>
			<li aria-current={$page.url.pathname === '/eksempler_kap_5' ? 'page' : undefined}>
				<a href="/eksempler_kap_5">Eksempler kap 5</a>
			</li>
			<li aria-current={$page.url.pathname === '/eksempler_kap_6' ? 'page' : undefined}>
				<a href="eksempler_kap_6">Eksempler kap 6</a>
			</li>
		</ul>
	</nav>
</header>
<main>
	<slot />
</main>
<style>
	ul {
		position: relative;
		padding: 0;
		margin: 0;
		height: 3em;
		display: flex;
		justify-content: center;
		align-items: center;
		list-style: none;
	}
	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 0.5rem;
		font-weight: 700;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	li[aria-current='page']{
		background-color: antiquewhite;
	}

</style>