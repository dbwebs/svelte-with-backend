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
      query singlePost($slug: String!) {
        post(where: { slug: $slug }) {
          title
          date
          content {
            html
          }
          tags
          author {
            id
            name
          }
        }
      }
    `

    const variables = {
      slug: context.params.slug,
    }

    const { post } = await graphcms.request(query, variables)

    return {
      props: {
        post,
      },
    }
  }
</script>

<script>
  export let post
</script>

<svelte:head>
  <title>{post.title}</title>
</svelte:head>

<h1>{post.title}</h1>
<p>{post.author.name}</p>
<p>{post.date}</p>
<p>{post.tags}</p>
{@html post.content.html}