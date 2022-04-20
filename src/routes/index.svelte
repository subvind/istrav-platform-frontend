
<script>
  import { onMount } from 'svelte';

  let loading = true
  let socialGroupSlug = ''
  let words = ["myfolder", "communityfolder", "com"]
  
  onMount(() => {
    let hostname = window.location.hostname
    if (hostname === 'localhost' || hostname === '127.0.0.1') {
      words = ["myfolder", "communityfolder", "com"]
    } else {
      words = hostname.split('.')

    }
    socialGroupSlug = words.slice((words.length - 3), words.length).join('.')
  })
</script>


<svelte:head>
  <title>/{words[0]}/</title>
</svelte:head>

<div class="container">
  <div class="community">
    <div class="folder">
      <div class="navigation">
        <a href="/login" class="btn btn-small teal lighten-2">LOGIN</a>
        <a href="/register" class="btn btn-small teal lighten-2">REGISTER</a>
        <a href="https://{words[1] + '.' + words[2]}" class="btn btn-small teal lighten-2">ROOT</a>
      </div>
      <div class="title">
        <a href="/">
          https://{socialGroupSlug}
        </a>
      </div>
      <div class="box">
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <div class="stamp">
          <a class="logo" href="/">
            /social_groups/{words[0]}/
          </a>
        </div>
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
        <br />
      </div>
    </div>
    <footer>© {new Date().getFullYear()} <a href="https://communityfolder.com">communityfolder.com</a>. All rights reserved.</footer>
  </div>
</div>

<style>
  .community {
    padding: 2em 0;
  }
  .folder {
    margin: 4em 0 1em 0;
    border: solid #222;
    border-width: 5px 5px 5px 5px;
  }

  .container {
    max-width: 900px;
    width: 100%;
    height: 100%;
    margin: 0 auto;
  }

  .box {
    background: #444;
  }

  footer {
    text-align: center;
  }

  a {
    color: inherit;
    text-decoration: none;
  }

  .title {
    display: flex;
    background-color: #444;
    font-size: 1.2em;
    width: fit-content;
    padding: 0.75em 0.5em;
    /* border-radius: 1em 1em 0 0; */
    border: solid #222;
    border-width: 5px 5px 0 5px;
    margin: -3em 0 -1em 1em;
    position: absolute;
  }

  .navigation {
    float: right;
    margin-top: -3em;
    background: #222;
    border: 5px solid #222;
    margin-right: 1em;
  }

  .pad {
    flex: 1;
  }
  
  .stamp {
    text-align: center;
  }

  .logo {
    background: #222;
    padding: 1em;
    font-size: 2em;
    margin: 3em auto;
    width: 100px;
  }
</style>