
<script>
  import { onMount } from 'svelte';
  
  import Navigation from '../components/Navigation.svelte'
  import NavigationAuth from '../components/NavigationAuth.svelte'
  import Breadcrumb from '../components/Breadcrumb.svelte';
  import Footer from '../components/Footer.svelte'
  import AllActivity from '../components/feed/AllActivity.svelte';

  let words = ["myfolder", "istrav", "net"]
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
      words = ["myfolder", "istrav", "net"]
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

<br />
<br />

<div class="wrapper container">
  <div class="row zero-margin">
    <div class="col s8">
      <Breadcrumb items={breadcrumbs} />
    </div>
    <div class="col s4">
      <div class="right" style="display: flex; margin: 1.5em 0;">
        <i class="material-icons" style="font-size: 1.2em;">refresh</i> <span style="margin-left: 0.5em;">This stream auto-updates.</span> 
      </div>
    </div>
  </div>

  <AllActivity />

  <div class="row zero-margin">
    <div class="col s8">
      <!-- <Welcome /> -->
    </div>
    <div class="col s4">
      <!-- <LatestBlogEntries /> -->
    </div>
  </div>
  <div class="row zero-margin">
    <div class="col s12">
      <Breadcrumb items={breadcrumbs} />
    </div>
  </div>
</div>

<br />
<br />

<Footer />

<style>
  .wrapper {
    min-height: 100vh;
  }
  .zero-margin {
    margin: 0;
  }
</style>