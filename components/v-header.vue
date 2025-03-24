<script setup lang="ts">
import GBIcon from '~/assets/icons/flags/gb.svg'
import IconLogo from '~/assets/icons/logo.svg'
import VButton from '~/components/ui/v-button.vue'

interface NavLink {
  title: string
  link: string
}

const navLinks: NavLink[] = [
  {
    title: 'Works',
    link: '/',
  },
  {
    title: 'About',
    link: '/about',
  },
]
</script>

<template>
  <header id="header">
    <IconLogo class="header-icon" />

    <nav class="header-nav">
      <ul class="header-nav__list">
        <li
          v-for="navLink in navLinks"
          :key="navLink.link"
          class="header-nav__list-item"
        >
          <NuxtLink
            class="header-nav__list-item__icon"
            :to="navLink.link"
          >
            {{ navLink.title }}
          </NuxtLink>
        </li>
      </ul>
    </nav>

    <div class="header-buttons__list">
      <VButton variant="rounded">
        <GBIcon :filled="true" />
      </VButton>
      <VButton class="header-buttons__list-action">
        Let's work
      </VButton>
    </div>
  </header>
</template>

<style scoped>
#header {
  min-height: 121px;
  padding: 0 40px;
  display: flex;
  align-items: center;
}

.header-icon {
  width: 84px;
  height: 25px;
  margin-right: auto;
}

.header-nav__list {
  display: flex;
  align-items: center;
  gap: 58px;
}

.header-nav__list-item > a {
  font-size: 20px;
  line-height: 100%;
}

.header-buttons__list {
  margin-left: 91px;
  display: flex;
  align-items: center;
  gap: 16px;
}

.header-buttons__list-action {
  max-width: 142px;
  height: 52px;
}
</style>
