<script context="module">
  import { gql, GraphQLClient } from 'graphql-request';

  /** @type {import('@sveltejs/kit').Load} */
  export async function load(context) {
    const graphcms = new GraphQLClient(
      import.meta.env.VITE_GRAPHCMS_URL,
      {
        headers: {},
      }
    )

    
    const query = gql`
    query singleProject($slug: String!) {
      project(where: { slug: $slug }) {
        title
        name
        coverPic
        {
          url
        }
        nowinfo
        prinfo
      }
    }
    `
    
    const variables = {
      slug: context.params.slug,
    }

    const { project } = await graphcms.request(query, variables)

    return {
      props: {
        project,
      },
    }
  }
</script>

<script>
  export let project;
</script>

<svelte:head>
  <title>{project.title}</title>
</svelte:head>

<div class="container-fluid p-5 text-center bg-primary">
  {#if project.name !== null}
    <h1>{project.name}</h1>
  {:else}
    <h1>{project.title}</h1>
  {/if}
  <img class="mw-100" src={project.coverPic.url} alt={project.title}>
</div>
<div class="p-3">
  <h2 class="text-light">Current Build</h2>
  <ul>
      {#each project.nowinfo as i}
          <li class="text-light">{i}</li>
      {/each}
  </ul>
  <h2 class="text-light">The Project</h2>
  <ul>
      {#each project.prinfo as i}
          <li class="text-light">{i}</li>
      {/each}
  </ul>
</div>