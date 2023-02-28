<script lang="ts">
  export let fill = "none";
  export let stroke = "currentColor";
  export let strokeWidth = 1.5;
  export let viewBox = "0 0 24 24";
</script>

<svg class={$$props.class} {fill} {stroke} stroke-width={strokeWidth} {viewBox} xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
  <path stroke-linecap="round" stroke-linejoin="round" d="M10.5 6a7.5 7.5 0 107.5 7.5h-7.5V6z"></path>
  <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 10.5H21A7.5 7.5 0 0013.5 3v7.5z"></path>
</svg>