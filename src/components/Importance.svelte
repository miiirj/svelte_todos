<script>
    export let importance;
    export let done;

    let options = [
        { number: 0, color: "green", text: "low" },
        { number: 1, color: "yellow", text: "medium" },
        { number: 2, color: "red", text: "high" },
    ];
</script>

<select bind:value={importance} class={options.find((o) => o.number == importance).color} disabled={done}>
    {#each options as option}
        <option selected={option.number == importance ? true : false} class={option.color} value={option.number}>
            {option.text}
        </option>
    {/each}
</select>

<style>
    .red {
        background-color: #f00;
    }

    .yellow {
        background-color: #ff0;
    }

    .green {
        background-color: #0f0;
    }
</style>
