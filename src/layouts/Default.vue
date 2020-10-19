<template>
  <main class="layout" role="main">
    <Header :siteName="$page.metadata.siteName" />
    <slot/>
    <div class="footer">
      <div class="footer-links">
        <a target="_blank" href="https://twitter.com/ChrisM4rk3r">Twitter</a>
        <a target="_blank" href="/sitemap.xml">Sitemap</a>
        <a target="_blank" href="/feed.xml">RSS Feed</a>
      </div>
    </div>
  </main>
</template>

<script>
import Header from "@/components/Header";

export default {
  components: {
    Header
  }
}
</script>

<style lang="scss">
:root {
    --app-background-color: #FFFFFF;
    --app-font-color: black;
}

[theme="dark"] {
    --app-background-color: #091A28;
    --app-font-color: white;
}

[theme="sepia"] {
    --app-background-color: #F1E7D0;
    --app-font-color:#433422;
}

body {
  background-color: var(--app-background-color);
  color: var(--app-font-color);
  font-family: "JosefinSans",-apple-system,system-ui,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;
  margin:0;
  padding:0;
  line-height: 1.5;
  font-size:1.1em;
}
h1 #title{
  font-family: "FrankRuhlLibre",Roboto,Arial,sans-serif;
}
h1 {
  font-family: "FrankRuhlLibreLight",Roboto,Arial,sans-serif;
}
.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}
.footer {
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-top:60px;
  font-size:.8em;
}

.footer a {
  color:gray;
}

.footer-links a {
  margin:0 4px;
}

a {
  border-bottom: 1px solid currentColor;
  color: rgb(63, 32, 201);
  text-decoration: none;

}
a:hover {
  border-bottom-color: currentColor;
  color: #686868;
}

@media only screen and (max-width: 500px) {
  .footer {
    flex-direction: column;
  }

  .header {
    h1 {
      font-size:1em;
    }
  }
}
  @font-face {
    font-family: JosefinSans;
    src: url('../assets/JosefinSans-Medium.ttf');
    font-weight: normal;
  }

    @font-face {
    font-family: FrankRuhlLibre;
    src: url('../assets/FrankRuhlLibre-Regular.ttf');
  }
  @font-face {
    font-family: FrankRuhlLibreLight;
    src: url('../assets/FrankRuhlLibre-Light.ttf');
  }
</style>