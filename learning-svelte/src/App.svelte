<script lang="ts">
  let name = 'Brittani'
  let src = '/sonic.jpg';
  import Nested from "./Nested.svelte";
</script>

<p>This is a paragraph</p>
<Nested />
<h1>Hello, {name.toUpperCase()}</h1>
<img src={src} alt="{name}" />

<style>
  p{
    color: blue;
    font-family: 'Comic Sans MS', cursive;
    font-size: 2em;
  }
</style>