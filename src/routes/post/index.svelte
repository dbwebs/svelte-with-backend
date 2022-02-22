<script context="module">
    import { gql, GraphQLClient } from 'graphql-request'
  
    export async function load() {
      const graphcms = new GraphQLClient(
        import.meta.env.VITE_GRAPHCMS_URL,
        {
          headers: {},
        }
      )
  
      const query = gql`
        query listPosts {
          posts {
            id
            title
            slug
            date
            excerpt
          }
        }
      `
  
      const { posts } = await graphcms.request(query)
  
      return {
        props: {
          posts,
        },
      }
    }
  </script>
  
  <script>
    export let posts
  </script>
  
  <h1>Page Header</h1>
  <ul>
    {#each posts as post}
    <li>
      <a href="/post/{post.slug}">{post.title}</a>
      {post.excerpt}
    </li>
    {/each}
  </ul>