<script setup>
  import MailIcon from "./MailIcon.vue"
  defineProps({
    link: {
      type: String,
      required: false
    }
  })
</script>

<template>
  <a href="#">
    <MailIcon/> <p>Subscribe to mail list</p>
  </a>
</template>

<style scoped>
  a{
    all:unset;
    cursor: pointer;
    background: var(--color-background-mute);
    width: fit-content;
    display: flex;
    flex-direction: row;
    padding: 10px 30px;
    border-radius: 10px;
    border: var(--color-border) solid 2px;
    align-items: center;
    gap: 10px;
  }
  a:hover{
    box-shadow: 0 2px 12px rgba(134, 134, 134, 0.4);
    transition: all 1s ease-in-out;
  }
</style>