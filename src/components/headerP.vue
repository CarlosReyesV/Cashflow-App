<template>
  <header>
    <img
      class="logoIcon"
      @click="reload"
      src="@/assets/Empire.png"
      alt="logoIcon"
    />
    <h1><span>Financial</span>-Life</h1>
    <h4><span>by Empire</span> Union Bank</h4>
  </header>
</template>

<script>
export default {
  methods: {
    reload() {
      location.reload();
    },
  },
};
</script>
