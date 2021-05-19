<script lang="ts">
  let posts: any[] = []
  let promise = Promise.resolve()

</script>

<h1>Welcome to SvelteKit</h1>

<div>
  {#each posts as post (post.id)}
    <h3>{post.title}</h3>
  {/each}
</div>


