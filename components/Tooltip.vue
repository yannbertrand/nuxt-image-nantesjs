<template>
  <div>
    <div class="tooltip tooltip-1">
      <p>Étape {{ stepNb }}/8</p>
      <p>
        <strong>{{ title }}</strong>
      </p>
      <table>
        <thead>
          <tr>
            <th></th>
            <th>transfered</th>
            <th>resources</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <th>before</th>
            <td>{{ transferedBefore ? transferedBefore : '- ' }}kB</td>
            <td>{{ resourcesBefore ? resourcesBefore : '- ' }}kB</td>
          </tr>
          <tr>
            <th>now</th>
            <td>{{ transferedNow }}kB</td>
            <td>{{ resourcesNow }}kB</td>
          </tr>
          <tr>
            <th>diff</th>
            <td>
              <template v-if="transferedDiff > 0"
                ><strong>↗ +{{ transferedDiff }}%</strong></template
              >
              <template v-else-if="transferedDiff === 0">-</template>
              <template v-else
                ><strong>↘ {{ transferedDiff }}%</strong></template
              >
            </td>
            <td>
              <template v-if="resourcesDiff > 0"
                ><strong>↗ +{{ resourcesDiff }}%</strong></template
              >
              <template v-else-if="resourcesDiff === 0">-</template>
              <template v-else
                ><strong>↘ {{ resourcesDiff }}%</strong></template
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="tooltip tooltip-2">
      <p class="link">
        <template v-if="previousLink"
          ><a :href="previousLink">&lt; previous</a></template
        >
        <template v-else>&lt; previous</template>
      </p>
    </div>
    <div class="tooltip tooltip-3">
      <p class="link">
        <template v-if="nextLink"><a :href="nextLink">next &gt;</a></template>
        <template v-else>next &gt;</template>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    stepNb: {
      type: Number,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    transferedBefore: {
      type: Number,
      required: false,
    },
    resourcesBefore: {
      type: Number,
      required: false,
    },
    transferedNow: {
      type: Number,
      required: true,
    },
    resourcesNow: {
      type: Number,
      required: true,
    },
    previousLink: {
      type: String,
      required: false,
    },
    nextLink: {
      type: String,
      required: false,
    },
  },
  methods: {
    calcPercent(before, now) {
      if (before !== undefined) {
        return Math.round(((now - before) / before) * 100)
      }
      return 0
    },
  },
  computed: {
    transferedDiff() {
      return this.calcPercent(this.transferedBefore, this.transferedNow)
    },
    resourcesDiff() {
      return this.calcPercent(this.resourcesBefore, this.resourcesNow)
    },
  },
}
</script>

<style>
.tooltip {
  position: fixed;
  right: 0;
  margin: 10px;
  padding: 10px;
  border: 3px solid DarkGreen;
  border-radius: 5px;
  background: SeaGreen;
  z-index: 1;
}
.tooltip-1 {
  top: 0;
}
.tooltip-2,
.tooltip-3 {
  top: 270px;
}
.tooltip-2 {
  right: 190px;
}
.tooltip p {
  color: white;
  padding: 0;
  text-align: center;
}
.tooltip strong {
  font-weight: bold;
}
.tooltip table {
  text-align: right;
  color: white;
  margin: 30px 5px 5px 5px;
}
.tooltip table th {
  font-weight: 500;
}
.tooltip table thead tr th {
  border-bottom: 1px solid black;
}
.tooltip table :is(th, td) {
  padding: 0 10px;
}
.tooltip table :is(th, td):not(:last-child) {
  border-right: 1px solid black;
}
.tooltip .link {
  margin: 0;
}
.tooltip .link a {
  color: white;
}
</style>
