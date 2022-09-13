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

<nav class="grey">
  <div class="nav-wrapper">
    <ul id="nav-mobile" class="">
      <li class={active === 'activity-feed' ? 'active' : ''}><a href="/" class="black-text">Activity Feed</a></li>
      <li class={active === 'forums' ? 'active' : ''}><a href="/forums" class="black-text">Forums</a></li>
      <li class={active === 'blogs' ? 'active' : ''}><a href="/blogs" class="black-text">Blogs</a></li>
      <li class={active === 'calendars' ? 'active' : ''}><a href="/calendars" class="black-text">Calendars</a></li>
      <li class={active === 'downloads' ? 'active' : ''}><a href="/downloads" class="black-text">Downloads</a></li>
      <li class={active === 'storefronts' ? 'active' : ''}><a href="/storefronts" class="black-text">Storefronts</a></li>
      <li class={active === 'leaderboards' ? 'active' : ''}><a href="/leaderboards" class="black-text">Leaderboards</a></li>
      <li class={active === 'referrals' ? 'active' : ''}><a href="/referrals" class="black-text">Referrals</a></li>
      <li class={active === 'rules' ? 'active' : ''}><a href="/rules" class="black-text">Rules</a></li>
    </ul>
    <ul id="nav-mobile" class="right hide-on-med-and-down">
      {#if authenticated}
        <li><a href={`/search`} class="black-text"><i class="material-icons">search</i></a></li>
        <li><a href={`/chats`} class="black-text"><i class="material-icons">question_answer</i></a></li>
        <li><a href={`/notifications`} class="black-text"><i class="material-icons">notifications</i></a></li>
        <li><a href={`/members/${token.id}`} class="black-text"><i class="material-icons">face</i></a></li>
      {:else}
        <li><a href="/auth/login" class="black-text"><i class="material-icons">power_settings_new</i></a></li>
      {/if}
    </ul>
  </div>
</nav>
    