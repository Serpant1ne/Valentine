
<script>
  export default{
    data(){
    	return{
        loaded: false,
        mainOpacity: 0,
        textColor: "red",
        designStyle: 1,
        companyName: ""
      }
  	},
    methods:{
      links: function(){
        console.log(this.$route)
      },
      checkRoute(){
        console.log('deployed');
        console.log($route)
      }
    },
    mounted(){
      this.links()
    },
    computed:{
    }
  }
</script>

<template>
  <header class="header mb-12">
    <div class="container mx-auto">
      <div class="section mx-6 py-6 flex">
        <a href="#" class="name text-3xl text-neutral-900">{{companyName}}</a>
        <button class="menu ml-auto"><img src="./img/Menu.svg" alt=""></button>
      </div>
    </div>
    
  </header>
  <main class="main mb-16">
    <div class="container mx-auto">
      <div class="section mx-6 text-neutral-900">
        <h1 class="text-2xl mb-12">Эта валентинка предназначена для <span class="name">Кати</span></h1>

        <div class="main-text relative flex mb-8">
          <img src="./img/Heart.svg" alt="" class="absolute heart blur-sm h-10 -rotate-34">
          <p class="text w-60 mx-auto text-lg my-4">Сначала мне казалось, что ты - лучшее, что есть в моей жизни, и что я тебя очень люблю... Но когда я
          подписывал(а) эту карточку, то понял(а), что ничего мне не показалось! Я люблю тебя с каждым днем все
          сильнее.</p>
          <img src="./img/Heart.svg" alt="" class="absolute heart blur-sm h-10 rotate-45 bottom-0 right-0">
        </div>

        <div class="sender ml-auto mr-8 w-max text-xl">
          <span>От: <span class="name">Андрея</span></span>
          </div>
      </div>
    </div>
  </main>
  <footer class="footer bg-pink-600 text-neutral-50">
    <div class="container mx-auto">
      <div class="section mx-6 py-6">
        <ul class="list-none text-lg space-y-3">
          <li class="logo text-2xl">Valentine</li>
          <li> <a href="#">О нас</a></li>
          <li><a href="#">Создать валентинку</a></li>
          <li><a href="#">Поддержать проект</a></li>
        </ul>
      </div>
    </div>
  </footer>
</template>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat&family=Pacifico&display=swap');

*{
    font-family: 'Montserrat';
    margin: 0;
    padding: 0;
}

.name, .logo{
    font-family: 'Pacifico';
}
  
</style>

