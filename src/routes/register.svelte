<script>
  import Register from "../components/auth/Register.svelte";
  import { onMount } from 'svelte';

  let words = ["myfolder", "communityfolder", "com"]
  
  onMount(() => {
    let hostname = window.location.hostname
    if (hostname === 'localhost' || hostname === '127.0.0.1') {
      words = ["myfolder", "communityfolder", "com"]
    } else {
      words = hostname.split('.')

    }
  })
</script>

<svelte:head>
  <title>{words[0]}: /community_folder/register</title>
  <meta name="description" content="">
  <meta name="keywords" content="">
</svelte:head>

<div class="container">
  <div class="community">
    <div class="folder">
      <div class="navigation">
        <a href="/login" class="btn btn-small blue lighten-2">LOGIN</a>
        <a href="/register" class="btn btn-small blue lighten-2">REGISTER</a>
        <a href="https://{words[1] + '.' + words[2]}" class="btn btn-small blue lighten-2">ROOT</a>
      </div>
      <div class="title">
        <a href="/">
          /community_folder/{words[0]}/
        </a>
      </div>
      <div class="box">
        <br />
        <br />
        <br />
        <br />
        <br />
        <div class="stamp">
          <a class="logo" href="/">
            /{words[0]}/register/
          </a>
        </div>
        <div class="single"></div>
        <Register />
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
    background-image: url("data:image/svg+xml,%3Csvg width='100' height='20' viewBox='0 0 100 20' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M21.184 20c.357-.13.72-.264 1.088-.402l1.768-.661C33.64 15.347 39.647 14 50 14c10.271 0 15.362 1.222 24.629 4.928.955.383 1.869.74 2.75 1.072h6.225c-2.51-.73-5.139-1.691-8.233-2.928C65.888 13.278 60.562 12 50 12c-10.626 0-16.855 1.397-26.66 5.063l-1.767.662c-2.475.923-4.66 1.674-6.724 2.275h6.335zm0-20C13.258 2.892 8.077 4 0 4V2c5.744 0 9.951-.574 14.85-2h6.334zM77.38 0C85.239 2.966 90.502 4 100 4V2c-6.842 0-11.386-.542-16.396-2h-6.225zM0 14c8.44 0 13.718-1.21 22.272-4.402l1.768-.661C33.64 5.347 39.647 4 50 4c10.271 0 15.362 1.222 24.629 4.928C84.112 12.722 89.438 14 100 14v-2c-10.271 0-15.362-1.222-24.629-4.928C65.888 3.278 60.562 2 50 2 39.374 2 33.145 3.397 23.34 7.063l-1.767.662C13.223 10.84 8.163 12 0 12v2z' fill='%23222222' fill-opacity='0.4' fill-rule='evenodd'/%3E%3C/svg%3E");
  }

  footer {
    text-align: center;
    color: #aaa;
  }

  a {
    color: inherit;
    text-decoration: none;
  }

  .title {
    display: flex;
    background-color: #444;
    background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='4' height='4' viewBox='0 0 4 4'%3E%3Cpath fill='%23111111' fill-opacity='1' d='M1 3h1v1H1V3zm2-2h1v1H3V1z'%3E%3C/path%3E%3C/svg%3E");
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

  .single {
    margin-bottom: -3em;
    height: 10em;
    width: 0;
    border-right: 1em solid #222;
    margin: 0 auto;
  }
</style>