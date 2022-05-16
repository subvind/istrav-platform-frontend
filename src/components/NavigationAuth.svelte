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
        <li><a href={`/search`}><i class="material-icons">search</i></a></li>
        <li><a href={`/chats`}><i class="material-icons">question_answer</i></a></li>
        <li><a href={`/notifications`}><i class="material-icons">notifications</i></a></li>
        <li><a href={`/members/${token.id}`}><i class="material-icons">face</i></a></li>
      {:else}
        <li><a href="/auth/login"><i class="material-icons">power_settings_new</i></a></li>
      {/if}
    </ul>
  </div>
</nav>
    