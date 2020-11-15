<template>
  <header class="header">
    <Logo/>
    <ClientOnly>
      <ThemeToggle />
    </ClientOnly>
  </header>
</template>

<script>
import Logo from "@/components/Logo";
export default {
  props: ["siteName"],
  components: {
    Logo,
    ThemeToggle: () => import('@/components/ThemeToggle')
  }
};
</script>

<style lang="scss">
  .header {
    display:flex;
    align-items: center;
    justify-content: space-between;
    a {
      color:inherit;
      border-bottom: none;
    }
  }
</style>
