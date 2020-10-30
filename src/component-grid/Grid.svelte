<script>
    import cssVars from "svelte-css-vars";

    export let columns = "1fr 1fr 1fr";
    export let rows = "1fr";
    export let rowGap = "20px";
    export let columnGap = "10px";

    $: styleVars = {
        columns,
        rows,
        rowGap,
        columnGap
    };
</script>

<style>
    div {
        display: grid;
        grid-template-columns: var(--columns);
        grid-template-rows: var(--rows);
        row-gap: var(--rowGap);
        column-gap: var(--columnGap);
    }
</style>

<div use:cssVars={styleVars}>
    <slot />
</div>
