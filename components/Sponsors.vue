<template>
  <div class="sponsors">
    <a class="sponsor" href="https://unirakun.fr/">
      <nuxt-img
        alt="unirakun"
        class="sponsor-logo-img"
        src="/sponsor/big_unirakun.png"
        width="156"
        height="130"
        format="webp"
      />
    </a>
    <a class="sponsor" href="https://seyos.fr/">
      <nuxt-img
        alt="seyos"
        class="sponsor-logo-img"
        src="/sponsor/seyos.png"
        width="156"
        height="68"
        format="webp"
      />
    </a>
    <a class="sponsor" href="https://nantes.zenika.com/#/">
      <nuxt-img
        alt="zenika"
        class="sponsor-logo-img"
        src="/sponsor/zenika.png"
        width="156"
        height="48"
        format="webp"
      />
    </a>
    <a class="sponsor" href="https://www.oxiane.bzh/">
      <nuxt-img
        alt="oxiane"
        class="sponsor-logo-img"
        src="/sponsor/oxiane.png"
        width="280"
        height="120"
        format="webp"
      />
    </a>
    <a class="sponsor" href="https://www.externatic.fr/">
      <nuxt-img
        alt="externatic"
        class="sponsor-logo-img"
        src="/sponsor/externatic.png"
        width="156"
        height="85"
        format="webp"
      />
    </a>
    <a class="sponsor" href="https://www.sfeir.com/">
      <nuxt-img
        alt="sfeir"
        class="sponsor-logo-img"
        src="/sponsor/sfeir.png"
        width="156"
        height="52"
        format="webp"
      />
    </a>
    <a class="sponsor" href="https://eleven-labs.com/">
      <nuxt-img
        alt="eleven labs"
        class="sponsor-logo-img"
        src="/sponsor/eleven-labs.png"
        width="156"
        height="106"
        format="webp"
      />
    </a>
    <a class="sponsor" href="https://www.lucca.fr/">
      <nuxt-img
        alt="lucca"
        class="sponsor-logo-img"
        src="/sponsor/logo-lucca.svg"
        width="156"
        height="55"
      />
    </a>
  </div>
</template>

<style>
.sponsors {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
}
.sponsor {
  flex: 0 0 20%;
  padding: 0 20px;
  display: flex;
  align-items: center;
}
.sponsor-logo-img {
  width: 100%;
  height: auto;
}
</style>
