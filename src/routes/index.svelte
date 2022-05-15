
<script>
  import { onMount } from 'svelte';
  
  import Navigation from '../components/Navigation.svelte'
  import NavigationAuth from '../components/NavigationAuth.svelte'
  import Breadcrumb from '../components/Breadcrumb.svelte';
  import Search from '../components/Search.svelte';

  let words = ["myfolder", "communityfolder", "com"]
  let breadcrumbs = [
    {
      label: 'Home',
      href: '/'
    },
    {
      label: 'Activity Feed',
      href: '/'
    },
  ]
  
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
  <title>/v/{words[0]}/ - Activity Feed</title>
</svelte:head>

<Navigation />

<NavigationAuth active="activity-feed" />

<div class="container">
  <div class="row">
    <div class="col s8">
      <Breadcrumb items={breadcrumbs} />
    </div>
    <div class="col s4">
      <Search />
    </div>
  </div>

  <div class="row">
    <div class="col s8">

    </div>
    <div class="col s4">
      
    </div>
  </div>
</div>