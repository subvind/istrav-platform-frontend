<script lang="ts">
  import { onMount } from "svelte";

  let host: string

  onMount(() => {
    host = window.location.host
  })
</script>

<footer>
  <nav class="white black-text">
    <div class="container">
      <div class="nav-wrapper">
        <ul class="">
          <li class=""><a href="/" target="_blank">{host} © {new Date().getFullYear()}.</a></li>
          <li class=""><a href="https://istrav.com" target="_blank">Made with &hearts; by isTrav.</a></li>
        </ul>
        <ul class="right">
          <li><a href={`https://istrav.com`}>Website</a></li>
          <li><a href={`https://istrav.live`}>Live</a></li>
          <li><a href={`https://istrav.dev`}>Headquarters</a></li>
          <li><a href={`https://istrav.info`}>Information</a></li>
        </ul>
      </div>
    </div>
  </nav>
</footer>

<style>
  footer {
    box-shadow: 0 0 5em #aaa;
  }
  footer ul li a {
    color: #111;
  }
</style>