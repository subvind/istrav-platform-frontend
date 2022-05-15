<script>
  import { onMount } from "svelte";

  export let subdomain = ''

  let hostname = 'communityfolder.com'
  let words = ["myfolder", "communityfolder", "com"]
  
  onMount(() => {
    hostname = window.location.hostname
    if (hostname === 'localhost' || hostname === '127.0.0.1') {
      hostname = 'communityfolder.com'
      words = ["myfolder", "communityfolder", "com"]
    } else {
      words = hostname.split('.')
    }
  })
</script>

<div class="row top">
  <div class="col m1" style="background: #111; text-align: center;">
    <nav class="green lighten-2">
      <div class="nav-wrapper">
        <a href="//communityfolder.com" class="brand-logo center"><i class="material-icons">folder_special</i></a>
      </div>
    </nav>
    <!-- <MainNavigation app={app} /> -->
  </div>
  <div class="col m3" style="background: #222;">
    <nav class="black lighten-2">
      <div class="nav-wrapper">
        <a href="/" class="brand-logo center subdomain">/v/{words[0]}/</a>
      </div>
    </nav>
    <!-- <Navigation app={app} active={active} /> -->
  </div>
  <div class="col m8">
    <div class="row header">
        <nav>
          <!-- {#if app === 'my-account'} -->
            <ul>
              <li>
                <a href="//communityfolder.com/marketing/solutions">Solutions</a>
              </li>
              <li>
                <a href="//communityfolder.com/marketing/product">Product</a>
              </li>
              <li>
                <a href="//communityfolder.com/marketing/pricing">Pricing</a>
              </li>
              <li>
                <a href="//communityfolder.com/marketing/about">About</a>
              </li>
              <li class="active">
                <a href="//www.communityfolder.com">Community</a>
              </li>
            </ul>
            <div class="right" style="margin: 0 1em;">
              <a class="btn grey lighten-2 black-text" href={`//${hostname}/create-social-group`}><i class="material-icons left" style="line-height: 37px;">add</i>SOCIAL GROUP</a>
            </div>
          <!-- {/if} -->
        </nav>
    </div>
  </div>
</div>
<div style="height: 4.5em;"></div>

<style>
  .subdomain {
    width: 100%;
  }
  .brand-logo i {
    margin: 0;
  }

  .top {
    z-index: 1000;
    position: fixed;
    right: 0;
    left: 0;
    margin: 0;
    padding: 0;
  }

  .top > .col {
    margin: 0;
    padding: 0;
  }

  .top > .col .row {
    margin: 0;
  }
</style>