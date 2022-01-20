<template>
  <div style="outline: none">
    <Tooltip
      title="Conclusion"
      :stepNb="9"
      :transferedNow="247"
      :resourcesNow="531"
      :transferedBefore="569"
      :resourcesBefore="833"
      previousLink="https://step-8--nuxt-image-nantesjs.netlify.app/"
    />
    <section class="layout">
      <header class="header">
        <div class="header-large-container" style="overflow: hidden">
          <nav class="header-nav">
            <a
              aria-current="page"
              class="logo-link"
              href="https://nantesjs.org/"
            >
              <Logo :width="104" :height="104" />
            </a>
            <div class="header-links">
              <div class="social-icons">
                <div class="social-icon">
                  <a
                    v-for="link of links"
                    :key="link.label"
                    class="social-icon-link"
                    :href="link.href"
                    :title="link.label"
                  >
                    <font-awesome-icon :icon="link.icon" class="fa-lg" />
                  </a>
                </div>
              </div>
              <div class="menu">
                <div class="menu-content">
                  <a
                    aria-current="page"
                    class="menu-link active"
                    href="https://nantesjs.org/"
                    >Evènements</a
                  ><a
                    class="menu-link"
                    href="https://nantesjs.org/contributeurs/"
                    >Contributeurs</a
                  ><a
                    class="menu-link"
                    href="https://nantesjs.org/code-de-conduite/"
                    >Code de conduite</a
                  ><a class="menu-link" href="https://nantesjs.org/a-propos/"
                    >A propos</a
                  ><a
                    target="_blank"
                    rel="noopener noreferrer"
                    href="https://conference-hall.io/public/event/DWIXMKeUnghfgJHerwEh"
                    class="menu-button"
                    >Proposer un sujet</a
                  >
                </div>
              </div>
            </div>
          </nav>
        </div>
      </header>

      <main class="main">
        <div class="large-container">
          <Nuxt />
        </div>
      </main>

      <footer class="footer">
        <a aria-current="page" class="footer-logo" href="https://nantesjs.org/">
          <Logo :width="60" :height="60" />
        </a>
        <p class="footer-copyright">
          <font-awesome-icon icon="heart" /> &nbsp;
          <a
            aria-current="page"
            class="footer-link"
            href="https://nantesjs.org/"
            >NantesJS</a
          >&nbsp; - © 2011-2022
          <a href="https://www.netlify.com" style="margin-left: 1rem">
            <img
              src="https://www.netlify.com/img/global/badges/netlify-light.svg"
              alt="Deploys by Netlify"
            />
          </a>
        </p>
      </footer>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      links: [
        {
          href: 'https://join.slack.com/t/nantesjs/shared_invite/enQtNTM0MjA0NTE0NTkzLTc3YWRkMjk3MTg3ZjEwYzVhYTA1YTA1OGE3MTdkMGE2ZjgzNzE1YzMwYWQwYmU0ZTEzNDhkZWUwZGY2ZjQ5OWY',
          label: 'Slack',
          icon: ['fab', 'slack'],
        },
        {
          href: 'https://twitter.com/NantesJS',
          label: 'Twitter',
          icon: ['fab', 'twitter'],
        },
        {
          href: 'https://github.com/yannbertrand/nuxt-image-nantesjs',
          label: 'Github',
          icon: ['fab', 'github'],
        },
        {
          href: 'https://nantesjs.org/rss.xml',
          label: 'RSS',
          icon: 'rss-square',
        },
        {
          href: 'https://www.youtube.com/c/NantesJS',
          label: 'YouTube',
          icon: ['fab', 'youtube'],
        },
        {
          href: 'https://twitch.tv/nantesjs',
          label: 'Twitch',
          icon: ['fab', 'twitch'],
        },
      ],
    }
  },
}
</script>

<style>
body {
  background-color: #f1f1f1;
  margin: 0;
  padding: 0;
}
* {
  font-family: Montserrat, sans-serif;
  font-weight: 300;
  line-height: 1.6em;
  box-sizing: border-box;
}
a,
a:visited,
p {
  color: #444;
}
p {
  text-align: justify;
}
h1,
h2,
h3 {
  color: #333;
  font-family: Fira Sans, sans-serif;
  font-weight: 400;
}
b {
  font-weight: 700;
}
.layout {
  min-height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
}
.header {
  align-items: center;
  background-color: #333;
  display: flex;
  padding: 10px 20px;
}
.header-large-container {
  width: 1160px;
  margin: auto;
  max-width: 100%;
}
.header-nav {
  align-items: center;
  display: flex;
  justify-content: space-between;
}
.logo-link {
  display: flex;
}
.logo-link .logo {
  max-height: 6.5rem;
  margin: auto;
}

.header-links {
  display: flex;
  flex-direction: column;
}
.social-icons {
  margin-bottom: 10px;
}
.social-icon {
  display: flex;
  justify-content: flex-end;
}
.social-icon-link:not(:last-child) {
  margin-right: 10px;
}
.social-icon-link {
  color: #f3e049 !important;
  height: 30px;
  width: 30px;
  border: 1px solid #333;
  border-radius: 1000px;
}
.menu-content {
  align-items: center;
  display: flex;
}
.menu-link {
  color: #f3e049 !important;
  font-family: 'Fira Sans', sans-serif;
  font-weight: 400;
  font-size: 18px;
  line-height: 2em;
  text-decoration: none;
  border-bottom: 3px solid #333;
  margin-right: 20px;
}
.menu-link.active {
  border-bottom: 3px solid #f3e049;
}
.menu-button {
  align-items: center;
  text-decoration: none;
  background-color: #f3e049;
  border: 0;
  color: #333;
  display: flex;
  font-family: 'Fira Sans', sans-serif;
  font-weight: 400;
  font-size: 18px;
  height: 40px;
  justify-content: center;
  margin: 0;
  padding: 0 10px;
}

.main {
  flex-grow: 1;
}

.large-container {
  width: 1160px;
  margin: auto;
  max-width: 100%;
}

.footer {
  margin-top: 40px;
  height: 7.5rem;
  background-color: #272727;
  position: relative;
}
.footer-logo {
  border-radius: 75px;
  width: 100px;
  height: 100px;
  padding: 20px;
  background-color: #272727;
  overflow: hidden;
  position: absolute;
  right: 40px;
  top: -45px;
  display: flex;
}
.footer-logo .logo {
  max-height: 75px;
  width: 100%;
  margin: auto;
}
.footer-copyright {
  color: #f3e049 !important;
  display: flex;
  align-items: center;
  height: 100%;
  margin: 0;
  justify-content: center;
}
.footer-link {
  color: #f3e049 !important;
}
</style>
