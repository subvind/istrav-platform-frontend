
<script>
  import { onMount } from 'svelte';

  import Navigation from '../../components/Navigation.svelte'
  import NavigationAuth from '../../components/NavigationAuth.svelte'

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
  <title>/v/{words[0]}/ - Referrals</title>
</svelte:head>

<Navigation />
<NavigationAuth active="referrals" />

