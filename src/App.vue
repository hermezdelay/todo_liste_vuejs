<script setup>
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <header>
    <div class="wrapper">

      <nav>
        <RouterLink to="/" class="bleu">Home</RouterLink>
        <RouterLink to="/about" class="bleu">About</RouterLink>
      </nav>
    </div>
  </header>
  <RouterView />
</template>
<style>
.bleu{
  color: #346a86;
}

</style>