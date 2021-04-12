<template>
  <main class="layout" role="main">
    <link
      rel="icon"
      type="image/png"
      href="https://i.ibb.co/B3b47Jc/logo.png"
    />
    <Header :siteName="$page.metadata.siteName" />
    <slot />
    <div class="footer">
      <div class="footer-links">
        <a target="_blank" href="https://twitter.com/cl3m3ntcode">Twitter</a>
        <a target="_blank" href="https://www.linkedin.com/in/cl%C3%A9ment-dev-06aa401a0/">LinkedIn</a>
        <a target="_blank" href="https://github.com/clement-dev">Github</a>
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
    Header,
  },
};
</script>

<style lang="scss">
:root {
  --app-background-color: #ffffff;
  --app-font-color: black;
  --app-icon-color: #5659dae6;
  --app-font-typo: "FrankRuhlLibreLight", Roboto, Arial, sans-serif;
}

[theme="dark"] {
  --app-background-color: #160a29;
  --app-font-color: white;
  --app-icon-color: #5659dae6
}

[theme="sepia"] {
  --app-background-color: #f1e7d0;
  --app-font-color: #433422;
  --app-icon-color: #5659dae6

}
[font="sans-serif"] {
  --app-font-typo: "Helvetica Neue", Helvetica, sans-serif, "Helvetica Roman", Icons;
}


body {
  background-color: var(--app-background-color);
  color: var(--app-font-color);
  font-family:"JosefinSans", -apple-system, system-ui, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  margin: 0;
  padding: 0;
  line-height: 1.5;
  font-size: 1.1em;
}
#title {
  font-size: 1.6em;
  font-weight: lighter;
  font-family: "Helvetica Neue", Helvetica, sans-serif, "Helvetica Roman", Icons;
}
h1 {
  font-size: 1.4em;
  font-family: "Helvetica Neue", Helvetica, sans-serif, "Helvetica Roman", Icons;
}
h2 {
  font-size: 1em;
  font-family: "Helvetica Neue", Helvetica, sans-serif, "Helvetica Roman", Icons;
}
h3 {
  font-size: 0.9em;
  font-family: "Helvetica Neue", Helvetica, sans-serif, "Helvetica Roman", Icons;
}
p {
font-family: var(--app-font-typo)
}
.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
}
.footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 10px;
  margin-top: 60px;
  font-size: 0.8em;
}

.footer a {
  color: gray;
}

.footer-links a {
  margin: 0 4px;
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
pre {
  border-radius: 14px;
  background: rgb(238, 233, 233) !important;
}
img {
  width:100%;
  border-radius: 16px;
}
blockquote {
  border-left: 5px solid #ccc;
  margin: 1.5em 10px;
  padding: 0.5em 10px;
  quotes: "\201C""\201D""\2018""\2019";
}
blockquote:before {
  line-height: 0.1em;
  margin-right: 0.25em;
  vertical-align: -0.4em;
}
blockquote p {
  display: inline;
  font-style: italic;
}

@media only screen and (max-width: 500px) {
  .footer {
    flex-direction: column;
  }

  .header {
    h1 {
      font-size: 1em;
    }
  }
}
@font-face {
  font-family: JosefinSans;
  src: url("../assets/JosefinSans-Medium.ttf");
  font-weight: normal;
}

@font-face {
  font-family: FrankRuhlLibre;
  src: url("../assets/FrankRuhlLibre-Regular.ttf");
}
@font-face {
  font-family: FrankRuhlLibreLight;
  src: url("../assets/FrankRuhlLibre-Light.ttf");
}
@font-face {
  font-family: SpaceMono-Regular;
  src: url("../assets/SpaceMono-Regular.ttf");
}
</style>
