<script lang="ts">
  let name = 'Brittani'
  let src = '/sonic.jpg';
  let string = `this string contains some <strong>HTML!!!</strong>`;
  import Nested from "./Nested.svelte";
</script>

<p>This is a paragraph</p>
<p>{@html string}</p>
<Nested />
<h1>Hello, {name.toUpperCase()}</h1>
<img src={src} alt="{name}" />

<style>
  p{
    color: goldenrod;
    font-family: 'Comic Sans MS', cursive;
    font-size: 2em;
  }
</style>