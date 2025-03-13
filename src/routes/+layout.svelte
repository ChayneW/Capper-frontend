<script>
  let { children } = $props();
  import "../app.css";
</script>

<div class="flex flex-col min-h-screen">
  {@render children()}
</div>

