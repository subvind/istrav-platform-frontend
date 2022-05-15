
<script>
  import { onMount } from 'svelte';
  
  import Navigation from '../../components/Navigation.svelte'
  import NavigationAuth from '../../components/NavigationAuth.svelte'
  import Breadcrumb from '../../components/Breadcrumb.svelte';
  import Search from '../../components/Search.svelte';
  import Welcome from '../../components/forums/Welcome.svelte';
  import LatestBlogEntries from '../../components/forums/LatestBlogEntries.svelte';

  let words = ["myfolder", "communityfolder", "com"]
  let breadcrumbs = [
    {
      label: 'Home',
      href: '/'
    },
    {
      label: 'Forums',
      href: '/forums'
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
  <title>/v/{words[0]}/ - Forums</title>
</svelte:head>

<Navigation />

<NavigationAuth active="forums" />

<br />
<br />

<div class="container">
  <div class="row zero-margin">
    <div class="col s8">
      <Breadcrumb items={breadcrumbs} />
    </div>
    <div class="col s4">
      <Search />
    </div>
  </div>

  <div class="row zero-margin">
    <div class="col s8">
      <Welcome />
    </div>
    <div class="col s4">
      <LatestBlogEntries />
    </div>
  </div>
</div>

<style>
  .zero-margin {
    margin: 0;
  }
</style>