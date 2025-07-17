<script>
    const emojis = {
        apple: '🍎',
        banana: '🍌',
        carrot: '🥕',
        doughnut: '🍩',
        egg: '🥚'
    };
    //name is updated whenever the prop value changes...
    let { name } = $props();

    const emoji = emojis[name];
</script>

<p>{emoji} = {name}</p>