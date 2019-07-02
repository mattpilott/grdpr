<h1>{post.title.rendered}</h1>

<div>{@html post.content.rendered}</div>

<script context="module">

   export async function preload(page) {

      const { slug } = page.params;
      const req = await this.fetch('https://eurogroupe.org/dev/wp/wp-json/wp/v2/news?slug=' + slug).then(r => r.json());

      return { post: req[0] };
   }
</script>

<script>
   export let post;
</script>