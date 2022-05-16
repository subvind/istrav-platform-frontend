<script>
  import { onMount } from "svelte";
  import { parseJwt } from '../parseJwt'

  export let active = 'activity-feed'
  let authenticated = false
  let token = {
    id: '',
    email: ''
  }

  onMount(() => {
    let lsToken = localStorage.getItem('token')
    if (lsToken) {
      token = parseJwt(lsToken)
    }

    if (token.email) {
      authenticated = true
    } else {
      authenticated = false
    }
  })
</script>

<footer>
  <nav class="white black-text">
    <div class="container">
      <div class="nav-wrapper">
        <ul class="">
          <li class=""><a href="https://communityfolder.com" target="_blank">CommunityFolder © {new Date().getFullYear()}.</a></li>
          <li class=""><a href="https://istrav.com" target="_blank">Made with ♥ by istrav.com.</a></li>
        </ul>
        <ul class="right">
          <li><a href={`/contact-us`}>Contact Us</a></li>
          <li><a href={`/privacy-policy`}>Privacy Policy</a></li>
          <li><a href={`/terms-and-conditions`}>Terms & Conditions</a></li>
        </ul>
      </div>
    </div>
  </nav>
</footer>

<style>
  footer ul li a {
    color: #111;
  }
</style>