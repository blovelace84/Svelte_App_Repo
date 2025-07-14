<script lang="ts">
  let name = 'Brittani'
  let src = '/sonic.jpg';
  let count = $state(0);
  let numbers = $state([1, 2, 3, 4]);
  function addNumber() {
    numbers[numbers.length] = numbers.length + 1;
  }
  function increment() {
    count += 1
  }
  let string = `this string contains some <strong>HTML!!!</strong>`;
  import Nested from "./Nested.svelte";
</script>

<p>This is a paragraph</p>
<p>{@html string}</p>
<Nested />
<h1>Hello, {name.toUpperCase()}</h1>
<img src={src} alt="{name}" />
<button onclick={increment}>
  Clicked {count}
  {count === 1 ? 'time' : 'times'}
</button>
<p>{numbers.join(' + ')} = ...</p>
<button onclick={addNumber}>
  Add a number
</button>
<style>
  p{
    color: goldenrod;
    font-family: 'Comic Sans MS', cursive;
    font-size: 2em;
  }
</style>