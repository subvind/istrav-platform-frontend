<script>
  export let items = [
    {
      label: '',
      href: ''
    }
  ]
</script>

<div class="explore right">
  <form>
    <div class="input-field">
      <input class="search" placeholder="Explore" />
    </div>
  </form>
</div>

<style>
  .explore {
    width: 100%;
  }

  .input-field {
    margin-top: 0.75em;
    padding-right: 2.5em;
  }
  
  .search {
    border-radius: 2em;
    padding: 0 1em;
    margin: 0 1em 0 0;
    background: #fff;
    color: #000 !important;
    box-shadow: 0 0 0.5em #aaa !important;
    position: relative;
    border-bottom: 0 !important;
  }
  .search:focus {
    border-bottom: 0 !important;
    box-shadow: 0 0 0.75em #555 !important;
  }
</style>