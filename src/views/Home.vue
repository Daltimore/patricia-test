<template>
  <section class="flex h-screen justify-center items-center">
    <div
      class="rounded-2xl bg-primary w-card
      h-card p-10 relative overflow-hidden
      patricia-bg"
    >
      <div class="flex justify-between items-center">
        <img src="@/assets/img/logo.svg" alt=""/>
        <div @click="handleChange" class="cursor-pointer">
          <img
            src="@/assets/img/eye-open.svg"
            alt=""
            v-if="show"
            class="object-contain w-6 h-6"
          >
          <img
            src="@/assets/img/eye-close.svg"
            alt=""
            v-else
            class="object-contain w-6 h-6"
          >
        </div>
      </div>
      <div>
        <div
          class="grid grid-cols-4 gap-6 text-secondary
          align-middle line-card"
          v-if="!show"
        >
          <p class="text-2xl font-semibold">••••</p>
          <p class="text-2xl font-semibold">••••</p>
          <p class="text-2xl font-semibold">••••</p>
          <p class="text-2xl">{{cardNumber.substr(cardNumber.length - 4)}}</p>
        </div>
        <div
          class="grid grid-cols-4 gap-6 text-secondary
          align-middle line-card"
          v-else
        >
          <p class="text-2xl">{{cardNumber.substr(0, 4)}}</p>
          <p class="text-2xl">{{cardNumber.substr(4, 4)}}</p>
          <p class="text-2xl">{{cardNumber.substr(8, 4)}}</p>
          <p class="text-2xl">{{cardNumber.substr(cardNumber.length - 4)}}</p>
        </div>
      </div>
      <div class="flex flex-row justify-between items-center align-bottom">
        <p
          v-if="!show"
          class="text-lg text-secondary"
        >
          CardHolders name
        </p>
        <p
          v-else
          class="text-lg text-secondary"
        >
          {{cardName}}
        </p>
        <div class="flex flex-row justify-between items-center">
          <div class="flex flex-col">
            <span class="uppercase text-tertiary text-xs">valid</span>
            <span class="uppercase text-tertiary -mt-1.5 text-xs">thru</span>
          </div>
          <p class="text-secondary text-xl pl-3">10/12</p>
        </div>
        <div
          class="flex flex-row justify-between items-center"
        >
          <span class="uppercase text-tertiary text-xs">cvv</span>
          <p
            v-if="!show"
            class="text-secondary text-xl pl-3"
          >
            •••
          </p>
          <p
            v-else
            class="text-secondary text-xl pl-3"
          >
            {{cvv}}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      show: false,
      cardNumber: '9784978497849784',
      cvv: 455,
      cardName: 'Anyanwu Leo .O'
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
  background-repeat: no-repeat;
  background-size: 87%;
  background-position: left -2.2rem top -1.8rem;
}

.line-card {
  line-height: 11.063rem;
  vertical-align: middle;
}

</style>