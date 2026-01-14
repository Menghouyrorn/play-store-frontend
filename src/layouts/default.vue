<template>
  <div>
    <Navbar />
    <div class="p-1">
      <RouterView></RouterView>
    </div>
  </div>
</template>

<script lang="ts" setup>
import Navbar from "@/components/shared/Navbar.vue";

</script>

<style></style>
