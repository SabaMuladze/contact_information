
<template>
  <div class="flex justify-center text-2xl md:text-4xl py-6">
    <h1>Contact Information</h1>
  </div>
  <div class="bg-blues flex flex-col px-6 py-4 md:rounded-xl">
    <div class="flex flex-col gap-2">
      <div class="flex flex-col">
        <label for="">User</label>
        <input v-model="user" type="text" class="bg-grays outline-none px-4 py-2">
      </div>
      <div class="flex flex-col">
        <label for="">Mobile Number</label>
        <input v-model="mobilePhone" type="number" class="bg-grays outline-none px-4 py-2">
      </div>
      <div class="flex flex-col">
        <label for="">Email</label>
        <input v-model="email" type="email" class="bg-grays outline-none px-4 py-2">
      </div>
      <div class="flex justify-center ">
        <button @click="addUser"
          class="px-8 py-2 bg-white hover:rounded-lg delay-75 ease-in-out hover:bg-grays hover:text-white">Add
          User</button>
      </div>
    </div>
    <div class="flex flex-col gap-6 mt-6">
      <div v-for="(card, index) in arr" :key="index" class="bg-grays rounded-lg p-4 flex items-center justify-between">
        <div>
          <h2>{{ card.user }}</h2>
          <h2>{{ card.mobilePhone }}</h2>
          <h2>{{ card.email }}</h2>
        </div>
        <div>
          <p @click="deleteUser(index)" class="text-3xl text-blues cursor-pointer">X</p>
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
    addUser() {
      let obj = { email: this.email, user: this.user, mobilePhone: this.mobilePhone }
      if (this.user.length > 2 && this.emailValidate(this.email) && this.mobilePhone > 8) {
        this.arr.push(obj)
        this.user = ''
        this.email = ''
        this.mobilePhone = ''
      }
      else {
        alert('Enter correct information')
      }
    },
    deleteUser(index) {
      this.arr.splice(index, 1)
    },
    validateEmail() {
      if (this.emailValidate(this.email)) {
        this.warning = false
        this.send()
      } else {
        this.warning = true
      }
    },
    emailValidate(email) {
      const emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/;
      return emailPattern.test(email);
    },
  },
}

</script>

<style scoped></style>
