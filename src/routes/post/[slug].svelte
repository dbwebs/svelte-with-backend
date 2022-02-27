<script context="module">
  import { gql, GraphQLClient } from 'graphql-request'

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
  export let project
</script>

<svelte:head>
  <title>{project.title}</title>
</svelte:head>

<h1>{project.title}</h1>