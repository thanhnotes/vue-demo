<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Vue.js App from Level 0"/>

    <div id="my-div">
      <input type="text" v-model="name">
      <h3 v-bind:title="message">{{name}}</h3>
    </div>

    <div id="app2">
      <span
        v-bind:title="message"
      >Rê chuột lên đây một vài giây để xem thuộc tính `title` được bind!</span>
    </div>

    <div>
      <button v-on:click="show = !show">Nói gì nào?</button>
      <transition name="slide-fade">
        <h3 v-if="show">Xin chào bạn của tôi!</h3>
      </transition>
    </div>

    <div>
      <ol>
        <li v-for="todo in todos" :key="todo">{{ todo.text }}</li>
      </ol>
    </div>

    <div class="list-rendering">
      <ul>
        <li v-for="(value, key, index) of myInfo" :key="key">{{index}} - {{key}} - {{value}}</li>
      </ul>
    </div>

    <div>
      <ul>
        <p>Danh sách đã hoàn thành</p>
        <li v-for="todo in listTodoCompleted" :key="todo">{{todo.text}}</li>
      </ul>
    </div>
    <div>
      <MyFirstComponent></MyFirstComponent>
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import MyFirstComponent from "@/components/MyFirstComponent.vue";

export default {
  name: "app",
  components: {
    HelloWorld,
    MyFirstComponent
  },
  data: function() {
    return {
      name: "Ai Đông Nâu",
      message: "Vào lúc " + new Date().toLocaleString(),
      show: false,
      todos: [
        { text: "Học JavaScript", isComplete: true },
        { text: "Học Vue", isComplete: true },
        { text: "Học React", isComplete: false },
        { text: "Xây dựng cái gì đó hay ho", isComplete: false },
        { text: "Xây dựng công trình", isComplete: true }
      ],
      myInfo: {
        name: "Laa Loo",
        age: "29",
        gender: "male",
        job: "Cốt đờ",
        address: "Đà Nẵng"
      }
    };
  },
  computed: {
    listTodoCompleted() {
      return this.todos.filter(item => !item.isComplete);
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
/*
  Animation cho enter và leave có thể có giá trị
  duration và timing function khác nhau.
*/
.slide-fade-enter-active {
  transition: all 0.3s ease;
}
.slide-fade-leave-active {
  transition: all 0.8s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-fade-enter, .slide-fade-leave-to
/* Trước 2.1.8 thì dùng .slide-fade-leave-active */ {
  transform: translateX(10px);
  opacity: 0;
}
</style>
