<script setup lang="ts">
const links = [
  {
    label: "Profile",
    avatar: {
      src: "https://avatars.githubusercontent.com/u/739984?v=4",
    },
  },
  {
    label: "Installation",
    icon: "i-heroicons-home",
    to: "/getting-started/installation",
  },
  {
    label: "Vertical Navigation",
    icon: "i-heroicons-chart-bar",
    to: "/components/vertical-navigation",
  },
  {
    label: "Command Palette",
    icon: "i-heroicons-command-line",
    to: "/components/command-palette",
  },
];

const ui = {
  container1: {
    base: "flex flex-col",
    padding: "",
  },
  container2: {
    base: "w-full flex flex-row items-start",
    padding: "",
  },
  sidebar: {
    mysidebar: {
      base: "flex-none",
    },
    card: {
      base: "mb-4",
      header: { padding: "px-1 py-1" },
      body: { padding: "" },
    },
  },
  main_container: {
    base: "flex-1",
    padding: "",
  },
};
</script>

<template>
  <UContainer :ui="ui.container1">
    <UiMyHeader :z-index="100">
      <UBadge> I Have a pen. </UBadge>
    </UiMyHeader>
    <UContainer :ui="ui.container2">
      <UiMySideBar :ui="ui.sidebar.mysidebar">
        <UCard :ui="ui.sidebar.card">
          <template #header> グループ１ </template>
          <UVerticalNavigation :links="links" />
        </UCard>
        <UCard :ui="ui.sidebar.card">
          <template #header> グループ２ </template>
          <UVerticalNavigation :links="links" />
        </UCard>
      </UiMySideBar>
      <UContainer :ui="ui.main_container">
        <slot />
      </UContainer>
    </UContainer>
  </UContainer>
</template>
