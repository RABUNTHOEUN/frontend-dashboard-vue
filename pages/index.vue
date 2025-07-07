<script lang="ts">
export const description = "A sidebar that collapses to icons.";
export const iframeHeight = "800px";
export const containerClass = "w-full h-full";
definePageMeta({
  layout: false,
});
import LoginForm from '~/components/LoginForm.vue';


</script>

<template>
  <div class="w-1/2 mx-auto my-20">
     <LoginForm />
  </div>
</template>
