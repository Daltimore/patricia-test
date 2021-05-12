<template>
  <section class="flex h-screen justify-center items-center">
    <div
      class="rounded-2xl bg-primary w-card
      h-card p-10 relative overflow-hidden
      patricia-bg"
    >
      <div class="flex justify-between items-center">
        <img src="@/assets/img/logo.svg" alt=""/>
        <div @click="handleChange">
          <img
            src="@/assets/img/eye-open.svg"
            alt=""
            v-if="show"
          >
          <img
            src="@/assets/img/eye-close.svg"
            alt=""
            v-else
          >
        </div>
      </div>
      <div>
        <div class="grid grid-cols-4 gap-6 text-secondary align-middle line-card">
          <p class="text-2xl font-semibold">••••</p>
          <p class="text-2xl font-semibold">••••</p>
          <p class="text-2xl font-semibold">••••</p>
          <p class="text-2xl">{{cardNumber.substr(cardNumber.length - 4)}}</p>
        </div>
      </div>
      <div class="align-bottom text-secondary">
        <p class="text-lg">CardHolders Name</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      cardNumber: '9784978497849784'
    }
  },
  methods: {
    handleChange() {
      this.show = !this.show;
    }
  }
}
</script>

<style>
.patricia-bg {
  background-image: url('../assets/img/patricia.png');
  background-size: 100%;
  background-position: top left;
}

.line-card {
  line-height: 11.063rem;
  vertical-align: middle;
}

</style>