<script lang="ts">
	import * as config from '$lib/config'
</script>

<footer>
	<div class="description">
	<p> <a href="https://github.com/Mariogil2001" target="_blank"  rel="noreferrer">{config.title}</a> &copy {new Date().getFullYear()}</p>
	<p> Gracias a <a href="https://www.youtube.com/@JoyofCodeDev" target="_blank"  rel="noreferrer">Joy of Code</a></p>
</div>
</footer>

<style>
	footer {
		padding-block: var(--size-7);
		border-top: 1px solid var(--border);
	}
	.description {
		display: flex;
		justify-content: space-between;
		align-items:center;
		flex-direction: row;
	}
	a {
		color: var(--brand);
	}
	a:hover
	{
		text-decoration: underline;
	}
	p {
		color: var(--text-2);
		font-size: var(--font-size-fluid-1);
		font-weight: var(--font-weight-6);
	}
</style>
