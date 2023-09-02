<script setup>
  import Post from "@/components/Post.vue";
  import { ref, onMounted } from 'vue';

  const posts = ref([]);

  onMounted(async () => {
    try {
      const response = await fetch('posts.json'); // Adjust the path to your JSON file
      if (response.ok) {
        posts.value = await response.json();
      } else {
        console.error('Failed to fetch posts data.');
      }
    } catch (error) {
      console.error('Error loading posts data:', error);
    }
  });
</script>

<template>
  <header>
    <div>
      <p>Hi World</p>
      <p>all will be well</p>
      <p>See ya.</p>
    </div>
    <img alt="Lavender profile picture" class="pfp" src="./assets/pfp.jpg" />
    <h1>lavender</h1>
  </header>
  <main>
    <div v-for="(post, index) in posts" :key="index">
      <Post
          :msg="post.msg"
          :title="post.title"
          :img="post.img"
          :spotifyLink="post.spotifyLink"
          :mailList="post.mailList"
      />
    </div>
  </main>
  <footer>
    <h4>Website made by <a href="https://azuyamat.com">Azuyamat</a></h4>
  </footer>
</template>


