<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  },
  title: {
    type: String,
    required: true
  },
  img: {
    type: String,
    required: false
  },
  spotifyLink: {
    type: String,
    required: false
  },
  mailList: {
    type: Boolean,
    required: false
  }
})

import ListenOnSpotify from "./ListenOnSpotify.vue"
import MailList from "./MailList.vue"
</script>

<template>
  <div class="post">
    <h2>{{title}}</h2>
    <p>{{msg}}</p>
    <img v-if="img != null" :src="img" alt="Cover album image">
    <ListenOnSpotify v-if="spotifyLink" :link="spotifyLink"/>
    <MailList v-if="mailList"/>
  </div>
</template>

<style scoped>
  .post{
    width: 60vw;
    padding: 30px;
    display: flex;
    flex-wrap: wrap;
    flex-direction: column;
    gap: 20px;

    background: var(--color-background-soft);
    border-radius: 10px;
    border: solid var(--color-border) 2px;
    box-shadow: 0 2px 12px rgba(134, 134, 134, 0.13);
  }

  .post h2{
    color:var(--lavender);
  }
  .post img{
    object-fit: cover;
    object-position: center;
    border-radius: 10px;
    max-width: 100%;
    max-height: 50%;
  }

  @media (max-width: 800px) {
    .post{
      width: 80vw;
    }
  }
</style>
