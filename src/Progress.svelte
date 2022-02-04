<div style:width={width}>{left}</div>

<script>
    export let percent = 0;

    $: width = percent/20 * 100 + '%'
    $: left = 20 - percent
</script>

<style>
    div {
        background-color: green;
    }
</style>