<script lang="ts">
export const description = "A sidebar that collapses to icons.";
export const iframeHeight = "800px";
export const containerClass = "w-full h-full";
definePageMeta({
  layout: "custom",
});
</script>

<template>
  <div class="flex flex-1 flex-col gap-4 p-4 pt-0">
    <h1 class="text-xl">Main Layout Content</h1>
    <div class="grid auto-rows-min gap-4 md:grid-cols-3">
      <div class="bg-muted/50 aspect-video rounded-xl" >1</div>
      <div class="bg-muted/50 aspect-video rounded-xl" >2</div>
      <div class="bg-muted/50 aspect-video rounded-xl" >3</div>
    </div>
    <div class="bg-muted/50 min-h-[100vh] flex-1 rounded-xl md:min-h-min" >4</div>
  </div>
</template>
