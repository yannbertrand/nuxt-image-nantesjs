<template>
  <div class="container">
    <article class="next-meetup">
      <div class="titlebar">
        <div class="titlebar-content">
          <div
            class="titlebar-image-wrapper"
            :style="nuxtBackgroundStyles"
          ></div>
          <div class="titlebar-infos">
            <h1>Meetup #63</h1>
            <p>
              Sponsorisé par <b>NantesJS</b><br />Hébergé par <b>NantesJS</b>
            </p>
          </div>
          <div class="titlebar-subcontent">
            <time datetime="2022-01-20" class="date"
              ><span class="date-column"
                ><span class="date-day">20</span
                ><span class="date-month">janv.</span></span
              ><span class="date-year">2022</span></time
            >
          </div>
        </div>
      </div>
      <div class="talks">
        <Talk
          v-for="talk of talks"
          :key="talk.title"
          :title="talk.title"
          :description="talk.description"
          :twitter="talk.twitter"
          :avatar="talk.avatar"
        />
      </div>
      <div class="buttons">
        <a class="button" href="https://youtu.be/KfJh14cyGpI">
          <font-awesome-icon :icon="['fab', 'youtube']" class="fa-lg" />
          &nbsp;Voir sur YouTube </a
        ><a class="button" href="https://twitch.tv/nantesjs">
          <font-awesome-icon :icon="['fab', 'twitch']" class="fa-lg" />
          &nbsp;Voir sur Twitch
        </a>
      </div>
    </article>

    <div class="full-width-container">
      <div class="full-width-background"></div>
      <div class="full-width-children">
        <h3 class="full-width-title">Sponsors</h3>
      </div>
    </div>

    <Sponsors />
  </div>
</template>

<script>
export default {
  data() {
    return {
      talks: [
        {
          title: 'Explorons les stratégies de caches offertent sur les PWA',
          description: `Quand on parle de PWA, il est question de Service Workers, c'est un fait. Etant donné que ce dernier nous permet de servir des fichiers hors-ligne, il est donc pertinent de se pencher sur les mécanismes de mises en cache proposés par ce dernier. A travers cette sessions, nous vous proposons de balayer les différentes et plus connues stratégies de mises en cache d'une PWA. Nous tacherons pour chacune de ces stratégies de vous proposer un exemple d'implémentation. Nous mettrons aussi le nez dans workbox qui pourra vous aider dans la mise en place de ces dernières. Les stratégies explorées seront les suivantes : - Cache-Only - Network-Only - Cache-First - Network-First - Cache-Then-Network - Stale-While-Revalidate - Generic-Fallback En terme de pré-requis, il es essentiel de comprendre le fonctionnement et le cycle de vie d'un Service Worker.`,
          twitter: 'jefbinomed',
          avatar:
            'https://pbs.twimg.com/profile_images/1191342264741695488/N-H7VyYL.jpg',
        },
        {
          title: 'Des images optimisées avec @nuxt/image',
          description: `Pour réaliser des sites statiques les plus performants, il est important d’utiliser des images aux formats adaptés et les plus légères possibles. Dans un contexte Nuxt, le plugin @nuxt/image nous aide à répondre à cette problématique tout en poussant les bonnes pratiques du moment en optimisant les Web Vitals afin de pour satisfaire l’algorithme de Google. Après une explication des enjeux, je vous propose de vous montrer un exemple concret de migration dans mon entreprise pour éviter quelques erreurs. *La connaissance de Vue.js et de Nuxt n'est pas un pré requis`,
          twitter: '_YannBertrand',
          avatar:
            'https://pbs.twimg.com/profile_images/756485011298258945/Cy3OcnnY.jpg',
        },
      ],
    }
  },
  computed: {
    nuxtBackgroundStyles() {
      const imgUrl = this.$img('/meetup/nuxt.png', {
        width: 176,
        height: 176,
        format: 'webp',
      })
      return {
        backgroundImage: `url('${imgUrl}')`,
      }
    },
  },
}
</script>

<style>
.container {
  margin: 0 auto;
  max-width: 1020px;
  padding: 0 20px;
}
.next-meetup {
  margin-top: 1rem;
}
.titlebar {
  display: flex;
  flex-direction: row;
  align-items: center;
  min-height: 15rem;
}
.titlebar-content {
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: center;
  min-height: 15rem;
}
.titlebar-image-wrapper {
  height: 11rem;
  width: 11rem;
  background-position: 50%;
  background-repeat: no-repeat;
  background-size: contain;
}
.titlebar-infos {
  margin-left: 2rem;
}
.titlebar-infos h1 {
  font-size: 5.8rem;
  font-weight: 700;
  line-height: 5.8rem;
  padding: 0;
  margin: 0;
}
.titlebar-infos p {
  font-size: 1.6rem;
  margin: 0;
}
.titlebar-subcontent {
  margin-left: auto;
}
.date {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  margin-left: auto;
  color: #333;
}
.date-column {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.date-day {
  font-size: 5.8rem;
  line-height: 4.8rem;
  font-weight: 700;
}
.date-month {
  font-size: 2rem;
}
.date-year {
  font-size: 2rem;
  font-weight: 700;
  letter-spacing: 0.1rem;
  -ms-writing-mode: tb-rl;
  writing-mode: vertical-rl;
  -webkit-text-orientation: upright;
  text-orientation: upright;
}

.talks {
  margin-top: 1rem;
}

.buttons {
  display: flex;
  margin-top: 20px;
  flex-direction: row;
  justify-content: center;
}
.button {
  color: #fff;
  background-color: #333;
  padding: 10px 15px;
  text-decoration: none;
}
.button + a {
  margin-left: 1rem;
}

.full-width-container {
  height: 8rem;
  margin: 2rem 0;
}
.full-width-background {
  position: absolute;
  left: 0;
  right: 0;
  height: inherit;
  background-color: #d8d8d8;
  z-index: 0;
}
.full-width-children {
  position: relative;
  height: 100%;
  display: flex;
  align-items: center;
}
.full-width-title {
  margin: 0;
  font-size: 1.8rem;
  font-weight: 300;
}
</style>
