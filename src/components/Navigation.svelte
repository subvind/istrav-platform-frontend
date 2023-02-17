<script>
  import { onMount } from "svelte";

  export let subdomain = ''

  let hostname = 'istrav.net'
  let words = ["myfolder", "istrav", "net"]
  
  onMount(() => {
    hostname = window.location.hostname
    if (hostname === 'localhost' || hostname === '127.0.0.1') {
      hostname = 'istrav.net'
      words = ["myfolder", "istrav", "net"]
    } else {
      words = hostname.split('.')
      hostname = [words.reverse()[1], words[0]].join('.')
      words.reverse() //  change back to in order for display
    }
  })
</script>

<div class="row top">
  <div class="col m1" style="background: #111; text-align: center;">
    <nav class="white">
      <div class="nav-wrapper">
        <ul>
          <li style="float: none;">
            <a href="https://istrav.net" alt="Front Gate" style="height: 64px;">
              <img src="/anchor.png" alt="about" style="height: 50px; margin: 0.5em 0;">
            </a>
          </li>
        </ul>
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
        <nav class="blue lighten-2">
          <!-- {#if app === 'my-account'} -->
            <ul>
              <li>
                <a href="//istrav.com/production" class="black-text">Production</a>
              </li>
              <li>
                <a href="//istrav.com/innovation" class="black-text">Innovation</a>
              </li>
              <li>
                <a href="//istrav.com/platforms" class="black-text">Platforms</a>
              </li>
              <li>
                <a href="//istrav.com/apps" class="black-text">Apps</a>
              </li>
              <li>
                <a href="//istrav.com/projects" class="black-text">Projects</a>
              </li>
            </ul>
            <div class="right" style="margin: 0 1em;">
              <a class="btn black white-text" href={`//${hostname}/create-social-group`}><i class="material-icons left" style="line-height: 37px;">add</i>Social Group</a>
            </div>
          <!-- {/if} -->
        </nav>
    </div>
  </div>
</div>
<div style="height: 4.6em;"></div>

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