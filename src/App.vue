
<template>
  <div class="bg-blues flex flex-col px-6 py-4">
    <div class="flex flex-col gap-2">
      <div class="flex flex-col">
        <label for="">User</label>
        <input type="text" class="bg-grays outline-none px-4 py-2">
      </div>
      <div class="flex flex-col">
        <label for="">Mobile Number</label>
        <input type="number" class="bg-grays outline-none px-4 py-2">
      </div>
      <div class="flex flex-col">
        <label for="">Email</label>
        <input type="email" class="bg-grays outline-none px-4 py-2">
      </div>
      <div class="flex justify-center ">
        <button class="px-8 py-2 bg-white hover:rounded-lg delay-75 ease-in-out">Add User</button>
      </div>
    </div>
    <div class="flex flex-col gap-6 mt-6">
      <div v-for="card in arr" :key="card.mobilePhone" class="bg-grays rounded-lg p-4 flex items-center justify-between">
        <div>
          <h2>{{ card.user }}</h2>
          <h2>{{ card.mobilePhone }}</h2>
          <h2>{{ card.email }}</h2>
        </div>
        <div>
          <p class="text-3xl text-blues cursor-pointer">X</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: '',
      mobilePhone: '',
      email: '',
      arr: [
        {
          user: 'Lucas',
          mobilePhone: '211254545',
          email: 'siliconeimpressions@hb-3tvm.com',
        },
        {
          user: 'John',
          mobilePhone: '019478148',
          email: 'janusezeal@recklesstech.club',
        },
        {
          user: 'Marie',
          mobilePhone: '991254345',
          email: 'malik99@donusumekatil.com',
        },
      ]
    }
  },
  methods: {

  },
}

</script>

<style scoped></style>
