<template>
  <div class="home">
    <h1>home</h1>
    <PostList v-if="showPosts" :posts="posts"/>
    <button @click="showPosts = !showPosts">togle posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostList from '@/components/PostList.vue';
import { ref } from 'vue';

export default {
  name: 'HomeView',
  components: {PostList},
  setup() {
    const posts = ref([
      {title: 'welcome to the blog', body: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Officiis consequuntur unde ipsam placeat quibusdam cupiditate molestias vitae culpa dolores commodi, accusamus quas laboriosam, sint nam optio laudantium repellendus deserunt mollitia assumenda molestiae harum obcaecati? Totam officiis labore aspernatur dignissimos porro architecto fugiat earum? Autem porro, repudiandae repellendus eius sequi fugiat tempora culpa velit esse vitae debitis voluptates. Provident deleniti sed doloribus laboriosam delectus temporibus, dolorum ratione, iusto iure voluptate officia! Voluptates earum, sequi quidem nostrum magnam ut dolor necessitatibus dolores, ipsa est repellat voluptate tenetur numquam consequatur voluptas. Architecto molestias sint suscipit illum sed adipisci eligendi dolores id! Doloremque, aut!', id: 1},
      {title: 'top 5 CSS tips', body: 'Lorem ipsum', id: 2},
    ])

    const showPosts = ref(true)
    return { posts, showPosts }
  }
}
</script>
