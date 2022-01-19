<template>
  <img
    class="logo"
    src="/nantesjs.svg"
    :width="width"
    :height="height"
    alt="Logo NantesJS"
  />
</template>

<script>
export default {
  props: {
    width: {
      type: Number,
      required: false,
    },
    height: {
      type: Number,
      required: false,
    },
  },
}
</script>
