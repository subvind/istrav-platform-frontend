<script>
  export let items = [
    {
      label: '',
      href: ''
    }
  ]
</script>

<nav class="breadcrumbs">
  <div class="nav-wrapper">
    <div class="col s12">
      {#each items as item}
        <a href={item.href} class="breadcrumb">{item.label}</a>
      {/each}
    </div>
  </div>
</nav>


<style>
  .breadcrumbs {
    background: transparent;
    box-shadow: none;
  }
  .breadcrumbs a {
    font-size: 12px;
    color: #555;

  }
  .breadcrumbs a::before {
    color: #555;
    font-size: 12px;
  }
</style>