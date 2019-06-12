<script>
  import Fetch from "./Fetch.svelte";
  import Form from "./Form.svelte";

  let searchTerm;

  function handleSubmit() {
	  const { value } = this.elements.search;
	  searchTerm = value;
  }
</script>

<Form {handleSubmit} />
<Fetch {searchTerm} let:data>
  <h1>A list of links</h1>
  <ul>
    {#each data as link}
      <li>
        <a href={link.url}>{link.title}</a>
      </li>
    {/each}
  </ul>
</Fetch>

