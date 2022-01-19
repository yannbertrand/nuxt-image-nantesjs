<template>
  <div class="talk">
    <div class="avatars">
      <div class="avatar" :style="speakerAvatarBackgroundStyles"></div>
    </div>
    <div>
      <h2 class="talk-title">
        {{ title }}
      </h2>
      <div class="talk-description">
        {{ description }}
      </div>
      <div class="talk-speaker">
        <font-awesome-icon :icon="['fab', 'twitter']" />
        &nbsp;<a :href="`https://twitter.com/${twitter}`">{{ twitter }}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    twitter: {
      type: String,
      required: true,
    },
    avatar: {
      type: String,
      required: true,
    },
  },
  computed: {
    speakerAvatarBackgroundStyles() {
      const imgUrl = this.$img(
        this.avatar,
        {
          width: 104,
          height: 104,
          radius: 'max',
          bg: 'F1F1F1',
        },
        { provider: 'imagekit' }
      )
      return {
        backgroundImage: `url('${imgUrl}')`,
      }
    },
  },
}
</script>

<style>
.talk {
  display: flex;
  flex-direction: row;
}
.avatars {
  flex: 0 0 6.5rem;
  position: relative;
  margin-top: 1rem;
  margin-right: 1rem;
  max-height: 6.5rem;
}
.avatar {
  height: 6.5rem;
  border-radius: 6.5rem;
  background-color: #ccc;
  background-size: cover;
}
.talk-title {
  margin: 1rem 1rem 0.5rem 0;
  font-weight: 600;
  font-size: 1.4rem;
}
.talk-description {
  margin: 0 0 0.5rem;
}
.talk-speakers {
  color: #333;
  display: flex;
  align-items: center;
}
</style>
