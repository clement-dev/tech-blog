<template>
  <Layout>
    <section class="posts">
      <div id="up">
        <a href="mailto:clement.is@protonmail.com">
        <div id="cover"></div>
        </a>
      </div>
      <PostList v-for="year in years" :key="year" :year="year" />
    </section>
  </Layout>
</template>

<script>
import PostList from "@/components/PostList";
export default {
  components: {
    PostList,
  },
  metaInfo: {
    title: "Tech Blog",
  },
  computed: {
    years() {
      const years = {};
      const posts = this.$page.allPost.edges;
      posts.map((post) => {
        const year = post.node.date.split(" ")[2];
        years[year] = "";
      });
      return Object.keys(years).sort((a, b) => {
        return b - a;
      });
    },
  },
};
</script>

<page-query>
query {
  metadata {
    siteName
    siteDescription
  }
  allPost(filter: { date: { gte: "2020" }}) {
    totalCount
    edges {
      node {
        id
        title
        timeToRead
        description
        date (format: "MMM D YYYY")
        path
      }
    }

  }
}
</page-query>

<style>
#up {
  position: relative;
  top: 0;
  transition: top ease 0.5s;
}
#up:hover {
  top: -10px;
}

#cover {
  border-radius: 16px;
  background-image: radial-gradient(
      circle farthest-corner at 84.6% 77.8%,
      rgba(86, 89, 218, 0.9) 0%,
      rgba(95, 208, 248, 0.5) 90%
    ),
    url("../../static/cover.jpg");
  width: 80%;
  height: 400px;
  background-size: cover;
  color: white;
  padding: 20px;
  opacity: 1;
  transition: 0.3s;
}
#cover:hover {
  opacity: 0.3;
  background-image: radial-gradient(
      circle farthest-corner at 84.6% 77.8%,
      rgba(86, 89, 218, 0.5) 0%,
      #5fd0f8e6 90%
    ),
    url("../../static/cover.jpg");
  -webkit-box-shadow: 10px 5px 35px 1px rgba(0, 0, 0, 0.36);
  -moz-box-shadow: 10px 5px 35px 1px rgba(0, 0, 0, 0.36);
  box-shadow: 10px 5px 35px 1px rgba(0, 0, 0, 0.36);
}
</style>
