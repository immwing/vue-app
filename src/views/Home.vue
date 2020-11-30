<template>
  <div class="content">
    <div class="posts">
      <div 
        v-for="post in posts"
        :key="post.index"
        class="post"
      >
        <div class="title" @click="to(post)">{{ post.title }}</div>
        <div class="date">{{ post.date }}</div>
        <div class="description">{{ post.description }}</div>
        <div class="pills">
          <router-link :to='"/tags/"+tag' v-for="tag in post.tags" :key="tag">
            <span>#{{ tag }}</span>
          </router-link>
        </div> 
        <hr>
      </div>
    </div>
  </div>
</template>

<script>
// import moment from 'moment'

export default {
  data() {
    return {
      posts: [
        {
          path: 'javascript-courses',
          title: 'Javascript courses',
          date: 'Nov 26 2020',
          description: '100 javascript practices',
          tags: ['javascript', 'vue', 'node', 'web design']
        },
        {
          path: '/vue-todo',
          title: 'Todo List',
          date: 'Nov 27 2020',
          description: 'Self designed todo app',
          tags: ['vue', 'javascript', 'html', 'css', 'bootstrap']
        }
      ]
    }
  },
  methods: {
    to(post) {
      // var date = moment(new Date(post.date)).format('YYYY/MM/DD')
      this.$router.push(post.path)
    }
  }
}
</script>


<style scoped>
.content {
  max-width: 760px;
  margin: 0 100px;;
  padding: 80px 20px;
}


.post .title {
  font-size: 40px;
  cursor: pointer;
  text-transform: capitalize;
}
.post .date {
  font-size: 14px;
  color: rgba(0,0,0,.6);
  margin-bottom: 16px;
}
.post .description {
  margin-bottom: 16px;
}
.post .pills a {
  display: inline-block;
  text-decoration: none;
  padding: 2px 5px;
  margin: 0 10px 10px 0;
  border-radius: 5px;
  background-color: #666;
  color: #fff;
}
</style>