<script context='module'>
	import { gql, GraphQLClient } from 'graphql-request'
  
  export async function load() {
	const graphcms = new GraphQLClient(
	  import.meta.env.VITE_GRAPHCMS_URL,
	  {
		headers: {},
	  }
	)

	const query = gql`
    query projectquery {
		projectLists {
            title
			projects {
				title
				slug
				description
				previewPic {
					url
				}
			}
		}
	}
	`;

	const { projectLists } = await graphcms.request(query)

	return {
	  props: {
		projectLists,
	  },
	}
  }
</script>

<script>
    export let projectLists;
</script>

<section id="projects" class="p-5 otherpage">
	<h1 class="text-light">List of Projects</h1>
	<p class="text-light">
		Here you can find all of the family projects we are planning and working on
	</p>
	<hr class="text-light" />
	{#each projectLists as li}
		<h1 class="text-light text-center">{li.title}</h1>
		<div class="row">
			{#each li.projects as p}
				<div class="col-md-4 py-3 mw-600 mx-auto">
					<div class="card">
						<img class="card-img-top" src={p.previewPic.url} alt={p.title} />
						<div class="card-body">
							<h4 class="card-title">{p.title}</h4>
							<p class="card-text">
								{p.description}
							</p>
							{#if p.slug !== null}
								<a href={p.slug} class="btn btn-primary">Learn more</a>
							{/if}
						</div>
					</div>
				</div>
			{/each}
		</div>
		<hr class="text-light" />
	{/each}
</section>
