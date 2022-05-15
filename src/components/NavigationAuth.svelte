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

<nav class="blue lighten-2">
  <div class="nav-wrapper">
    <ul id="nav-mobile" class="">
      <li class={active === 'activity-feed' ? 'active' : ''}><a href="/">Activity Feed</a></li>
      <li class={active === 'forums' ? 'active' : ''}><a href="/forums">Forums</a></li>
      <li class={active === 'blogs' ? 'active' : ''}><a href="/blogs">Blogs</a></li>
      <li class={active === 'calendars' ? 'active' : ''}><a href="/calendars">Calendars</a></li>
      <li class={active === 'downloads' ? 'active' : ''}><a href="/downloads">Downloads</a></li>
      <li class={active === 'storefronts' ? 'active' : ''}><a href="/storefronts">Storefronts</a></li>
      <li class={active === 'leaderboards' ? 'active' : ''}><a href="/leaderboards">Leaderboards</a></li>
      <li class={active === 'referrals' ? 'active' : ''}><a href="/referrals">Referrals</a></li>
      <li class={active === 'rules' ? 'active' : ''}><a href="/rules">Rules</a></li>
    </ul>
    <ul id="nav-mobile" class="right hide-on-med-and-down">
      {#if authenticated}
        <li><a href={`/accounts/${token.id}`}>{token.email}</a></li>
      {:else}
        <li><a href="/auth/login">Login</a></li>
        <li><a href="/auth/register">Register</a></li>
      {/if}
    </ul>
  </div>
</nav>
    