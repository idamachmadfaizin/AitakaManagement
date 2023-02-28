<script lang="ts">
    export let fill = "none";
    export let stroke = "currentColor";
    export let strokeWidth = 1.5;
    export let viewBox = "0 0 24 24";
</script>

<svg class={$$props.class} {fill} {stroke} stroke-width={strokeWidth} {viewBox} xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
    <path stroke-linecap="round" stroke-linejoin="round" d="M21 7.5l-9-5.25L3 7.5m18 0l-9 5.25m9-5.25v9l-9 5.25M3 7.5l9 5.25M3 7.5v9l9 5.25m0-9v9"></path>
</svg>