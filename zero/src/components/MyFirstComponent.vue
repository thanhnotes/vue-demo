<template>
  <div class="my-first-component">
    <div>{{message}}</div>
    <div>
      <button @click="sayHello">Click me!</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: "I am a Text"
    };
  },
  methods: {
    sayHello() {
      this.message = "this is new message"
    }
  },
  computed:{
      reversedMessage(){
          return this.message.split('').reverse().join()
      }
  },
  watch:{
      message(){
          console.log('Message was changed')
      },
      reversedMessage(){
          console.log('Computed was changed')
      }
  }
};
</script>

<style lang="css" scoped>
.my-first-component {
  color: orange;
}
</style>


