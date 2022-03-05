<script context="module">
	import { gql, GraphQLClient } from 'graphql-request';

	export async function load() {
		const graphcms = new GraphQLClient(import.meta.env.VITE_GRAPHCMS_URL, {
			headers: {}
		});

		const query = gql`
			query list {
				articlelists {
					title
					articles {
						title
						description
						slug
						prepic {
							url
						}
					}
				}
			}
		`;

		const { articlelists } = await graphcms.request(query);

		return {
			props: {
				articlelists
			}
		};
	}
</script>

<script>
	export let articlelists;
</script>


<section id="articles" class="p-5">
	<h1 class="text-light">List of Articles</h1>
	<p class="text-light">
		Here we talk about topics that are important to us and our great experiences
	</p>

	<hr class="text-light" />
	{#each articlelists as li}
		<h1 class="text-light text-center">{li.title}</h1>
		<div class="row">
			{#each li.articles as p}
				<div class="col-md-4 py-3 mw-600 mx-auto">
					<div class="card">
						<img class="card-img-top" src={p.prepic.url} alt={p.title} />
						<div class="card-body">
							<h4 class="card-title">{p.title}</h4>
							<p class="card-text">
								{p.description}
							</p>
							{#if p.slug !== ''}
								<a href="/articles/{p.slug}" class="btn btn-primary">Learn more</a>
							{/if}
						</div>
					</div>
				</div>
			{/each}
		</div>
		<hr class="text-light" />
	{/each}
</section>
