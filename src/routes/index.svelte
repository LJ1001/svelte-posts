<script lang="ts">
  let fetchData = fetchPosts()
  async function fetchPosts (): Promise<any[]> {
    const res = await fetch('https://serverless-api.tutorial1234.workers.dev/api/posts');
    return res.json()
  }

</script>

<h1>Welcome to SvelteKit</h1>

{#await fetchData}
	<p>...waiting</p>
{:then posts}
  <div>
    {#each posts as post (post.id)}
      <h3>{post.title}</h3>
    {/each}
  </div>
{:catch error}
	{error.message}
{/await}



