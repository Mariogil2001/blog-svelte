<script lang="ts">
	import { formatDate } from '$lib/utils'
	import * as config from '$lib/config'

	export let data
</script>

<svelte:head>
	<title>{config.title}</title>
</svelte:head>

<section>
	<ul class="posts">
		{#each data.posts as post}
			<li class="post">
				<a href={post.slug} class="title">{post.title}</a>
				<div>

				{#each post.categories as category}
						<p class="category">{category}</p>
					
				{/each}
			</div>
				<p class="description">{post.description}</p>
				<p class="date">{formatDate(post.date)}</p>
			</li>
		{/each}
	</ul>
</section>

<style>
	section {
		display: flex;
		justify-content: center;
		align-items: center;
		font-family: var(--font-mono);
		font-weight: var(--font-weight-5);
	}
	.posts {
		display: grid;
		gap: var(--size-7);
	}

	.post {
		max-inline-size: var(--size-content-3);
	}

	.post:not(:last-child) {
		border-bottom: 1px solid var(--border);
		padding-bottom: var(--size-7);
	}

	.title {
		font-size: var(--font-size-fluid-3);
		color: var(--brand);
		text-transform: capitalize;
		text-align: center;
		display: flex;
		justify-content: center;
	}
	.title:hover {
		text-decoration: underline;
		cursor: pointer;
	}
	.date,
	div {
		color: var(--text-2);
		text-align: center;
		display: flex;
		justify-content: center;
	}
	.date{
		margin-top: .6em;
	
	}
	.category {
		text-transform: uppercase;
		width: fit-content;
		background-color: var(--surface-3);
		border-radius: 10px;
		padding: 0.2em 0.6em;
		margin-inline: .2em;
	}

	.date:hover {
		text-decoration: underline;
		cursor: default;
	}

	.description {
		margin-top: var(--size-3);
	}
</style>
