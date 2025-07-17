<script lang="ts">
  let name = 'Brittani'
  let src = '/sonic.jpg';
  const colors = ['red', 'orange', 'yellow', 'green', 'blue', 'indigo', 'violet'];
  let selected = $state(colors[0]);
  import Counter from "./Counter.svelte";
  let elapsed = $state(0);
  let interval = $state(1000);
  let count = $state(0);
  let numbers = $state([1, 2, 3, 4]);
  let total = $derived(numbers.reduce((t, n) => t + n, 0));
  function addNumber() {
    numbers.push(numbers.length + 1);
    console.log($state.snapshot(numbers));
  }

  $effect(() => {
    const id = setInterval(() => {
      elapsed += 1;
    }, interval);
    return () => {
      clearInterval(id);
    };
  });
  const pkg = {
    name: 'svelte',
    version: 5,
    description: 'blazing fast',
    website: 'https://svelt.dev'
  };
  $inspect(numbers);
  function increment() {
    count += 1
  }
  let string = `this string contains some <strong>HTML!!!</strong>`;
  import Nested from "./Nested.svelte";
    import PackageInfo from "./PackageInfo.svelte";
</script>

<p>This is a paragraph</p>
<p>{@html string}</p>
<Nested />
<PackageInfo {...pkg}/>
<Nested answer={"42"}/>
<Counter />
<Counter />
<Counter />
<h1>Hello, {name.toUpperCase()}</h1>
<h1 style="color: {selected}">Pick a colour</h1>
<div>
  {#each colors as color, i}
    <button
      style="background: {color}"
      aria-label={color}
      aria-current={selected === color}
      onclick={() => selected = color}
    >{i + 1}</button>
  {/each}
</div>
<img src={src} alt="{name}" />
<button onclick={increment}>
  Clicked {count}
  {count === 1 ? 'time' : 'times'}
</button>
{#if count > 10}
<p>{count} is greater than 10</p>
{:else if count < 5}
<p>{count} is less than 5</p>
{:else}
  <p>{count} is between 5 and 10</p>
{/if}
<p>{numbers.join(' + ')} = {total}</p>
<button onclick={addNumber}>
  Add a number
</button>
<button onclick={() => interval /=2}>speed up</button>
<button onclick={() => interval *=2}>slow down</button>
<p>elapsed: {elapsed}</p>
<style>
  p{
    color: goldenrod;
    font-family: 'Comic Sans MS', cursive;
    font-size: 2em;
  }
</style>