<script setup>
import { useRoute } from 'vitepress'
import { computed } from 'vue'

const route = useRoute()

const isHome = computed(() => route.path === '/')

const navLinks = [
  { text: 'About', href: '#about' },
  { text: 'Experience', href: '#experience' },
  { text: 'Connect', href: '#connect' },
]
</script>

<template>
  <div class="page-wrap">
    <nav class="nav">
      <div class="nav-inner">
        <a href="/" class="nav-name">Colleen <strong>Peoples</strong></a>
        <ul class="nav-links" v-if="isHome">
          <li v-for="link in navLinks" :key="link.href">
            <a :href="link.href">{{ link.text }}</a>
          </li>
        </ul>
      </div>
    </nav>
    <Content />
  </div>
</template>
