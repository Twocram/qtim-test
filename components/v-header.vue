<script setup lang="ts">
import IconLogo from "~/assets/icons/logo.svg";
import GBIcon from "~/assets/icons/flags/gb.svg"
import VButton from "~/components/ui/v-button.vue";

interface NavLink {
  title: string;
  href: string;
}

const navLinks: NavLink[] = [
  {
    title: "Works",
    href: "/",
  },
  {
    title: "About",
    href: "/about",
  },
];
</script>

<template>
  <header id="header">
    <IconLogo class="header-icon" />

    <nav class="header-nav">
      <ul class="header-nav__list">
        <li
          class="header-nav__list-item"
          v-for="link in navLinks"
          :key="link.title"
        >
          <NuxtLink class="header-nav__list-item__icon" :to="link.href">{{ link.title }}</NuxtLink>
        </li>
      </ul>
    </nav>

    <div class="header-buttons__list">
      <v-button variant="rounded">
        <GBIcon :filled="true" />
      </v-button>
      <v-button class="header-buttons__list-action">
        Let's work
      </v-button>
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
