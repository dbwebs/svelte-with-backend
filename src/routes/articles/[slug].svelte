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
        query singleArticle($slug: String!) {
          article(where: { slug: $slug }) {
            title
            content
            coverPic
            {
                url
            }
            prepic
            {
                url
            }
          }
        }
      `
  
      const variables = {
        slug: context.params.slug,
      }
  
      const { article } = await graphcms.request(query, variables)
  
      return {
        props: {
          article,
        },
      }
    }
  </script>
  
  <script>
    export let article
  </script>

  <svelte:head>
    <title>{article.title}</title>
  </svelte:head>

<section id="health-article">
	<img class="mw-100" src={article.coverPic.url} alt="Vegetables and fruits" />
	<div class="p-5">
		
  
  <h1 class="text-light">{article.title}</h1>
  {#each article.content as i}
    <p class="text-light">{i}</p>
  {/each}
		<img class="mw-600 mx-auto w-100" src={article.prepic.url} alt="fruits and vegetables">

	</div>
</section>
