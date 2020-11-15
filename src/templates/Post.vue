<template>
  <Layout>
    <div class="article">
      <h1 class="article-title">{{$page.post.title}}</h1>
      <p class="article-date"> {{ $page.post.date}} · <i>{{$page.post.timeToRead}} min read</i></p>
      <article v-html="$page.post.content" />
    </div>
    <Disqus shortname="clement-dev" :identifier="$page.post.title" />
  </Layout>
</template>

<script>
import Header from "@/components/Header";
export default {
  components: {
    Header
  }
};
</script>


<page-query>
query Post ($path: String!) {
  metadata {
    siteName
    siteDescription
  }
   post: post (path: $path) {
    id
    title
    content
    date (format: "D MMMM YYYY")
    timeToRead
  }
}
</page-query>

<style>
  .article {
    margin-top: 15px;
    font-family:  var(--app-font-typo)
  }

  .article-title {
    font-size: 1.8em;
    text-align: center;
    margin-bottom:0;
  }

  .article-date {
    text-align: center;
    color: var(--app-font-color);
    margin-top:0;
    font-size:.8em;
  }

  .article blockquote {
    padding: 10px 20px;
    margin: 0 0 20px;
    font-size: 17.5px;
  }

  .article table {
    width: 100%;
    max-width: 100%;
    margin-bottom: 20px;
  }

  .article th {
    font-family: "Helvetica Neue", Helvetica, sans-serif, "Helvetica Roman", Icons;
    font-size: 0.8em;
    vertical-align: bottom;
  }

  .article td {
      padding: 8px;
      line-height: 1.42857143;
      vertical-align: top;
      text-justify: auto;

  }

  .article tr:nth-child(odd) td {
    background-color: var(--app-background-color);
  }

  .article img {
    margin:auto;
    width:90%;
    display:block;
    margin:10px auto;
  }
</style>
