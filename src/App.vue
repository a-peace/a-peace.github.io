<template>
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">
  <img id="avatar" alt="my avatar" src="./assets/avatar.png">
  <p>Автор картинки <a href="https://twitter.com/SH0R0KEN" class="ref">@SH0R0KEN</a> </p>
  
  <p>Пока данный сайт Состоит из одной странички и не несет никакой информации и функционала </p>
   <p class="">Так что вот вам кнопка, чтобы развлечься</p>
   <button type="button" :class="classButton" @click="changeClass"

    >Нажми на меня</button>
  
    <p v-show="clicks">{{clicks}}</p>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  mounted() {
    let src = document.getElementById("avatar").src
    console.log('%cНе ожидали?', 'color: blue');
    console.log('%cДа, я тоже тут', 'color: blue');
    console.log('%c ', 'font-size:500px; background:url('+ src +') no-repeat;');
  },
  data: function () {
    return {
      clicks: 0, 
      classButton: 'btn btn-primary',
      listOfClasses: ["btn btn-primary", "btn btn-secondary", "btn btn-success", 
                      "btn btn-danger", "btn btn-warning", "btn btn-info", 
                      "btn btn-light", "btn btn-dark"]
    };
  },
  methods: {
    changeClass(){
      let lenght = this.listOfClasses.length - 1;
      let index = this.listOfClasses.map(function(e) { return e; }).indexOf(this.classButton);
      if (lenght == index) {index = -1}
      this.classButton = this.listOfClasses[index + 1];
      this.clicks += 1;
    },
    
  }
}
</script>

<style>
#app, footer {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
footer kek.line-through{ 
  text-decoration: line-through; 
}
</style>
