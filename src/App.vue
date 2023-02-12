
<script>
import { useRoute, useRouter } from 'vue-router';
export default{
  
    data(){
    	return{
        loaded: false,
        mainOpacity: 0,
        accent: "#DB2777",
        receiverName: "Тебя!",
        mainText: "Whoopsie-woo",
        senderName: "...",
      }
  	}, 
    methods:{
      async checkRoute(){
        const ROUTER = useRouter()
        console.log('deployed');
        await ROUTER.isReady()
        console.log(this.$route.query.design)
        if(this.$route.query.design){
          if(this.$route.query.design === "Classic"){
            this.accent = 'DB2777'
          }
          else if(this.$route.query.design === "Romantic"){
            this.accent = '#BE123C'
          }
          else if(this.$route.query.design === "Passion"){
            this.accent = '#DC2626'
          }
          else if(this.$route.query.design === "Charm"){
            this.accent = '#A21CAF'
          }
        }
        if(this.$route.query.recieverName){
          this.receiverName = this.$route.query.recieverName
        }
        if(this.$route.query.senderName){
          this.senderName = this.$route.query.senderName
        }
        if(this.$route.query.mainText){
          this.mainText = this.$route.query.mainText
        }
        
      },
      set(){
        let timeout = setTimeout(this.hideLoading, 500)
      },
      hideLoading(){
        this.loaded = true;
        this.mainOpacity = 1
      },
      checkHeight(){
        const wrapper = document.getElementById('mainPart')
        const screenHeight = screen.height

        console.log(screenHeight)
        console.log(wrapper.clientHeight)

        if(screenHeight > wrapper.clientHeight){
          console.log('relatived')
          wrapper.classList.add('relative', 'min-h-screen')
          const footer = document.getElementById('footer');
          footer.classList.add('absolute', 'bottom-0', 'w-full')
          
        }
        
      }
    },
    mounted(){
      this.checkRoute()
      this.set()
      this.checkHeight()
    },
    computed:{

    }
  }
</script>

<template>
  <div class="loading w-full h-full fixed bg-neutral-50 grid place-items-center" :class="{hidden: loaded}">
    <svg aria-hidden="true" class="w-16 h-16 text-neutral-200 animate-spin dark:text-neutral-200 " viewBox="0 0 100 101" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M100 50.5908C100 78.2051 77.6142 100.591 50 100.591C22.3858 100.591 0 78.2051 0 50.5908C0 22.9766 22.3858 0.59082 50 0.59082C77.6142 0.59082 100 22.9766 100 50.5908ZM9.08144 50.5908C9.08144 73.1895 27.4013 91.5094 50 91.5094C72.5987 91.5094 90.9186 73.1895 90.9186 50.5908C90.9186 27.9921 72.5987 9.67226 50 9.67226C27.4013 9.67226 9.08144 27.9921 9.08144 50.5908Z" fill="currentColor"/>
        <path d="M93.9676 39.0409C96.393 38.4038 97.8624 35.9116 97.0079 33.5539C95.2932 28.8227 92.871 24.3692 89.8167 20.348C85.8452 15.1192 80.8826 10.7238 75.2124 7.41289C69.5422 4.10194 63.2754 1.94025 56.7698 1.05124C51.7666 0.367541 46.6976 0.446843 41.7345 1.27873C39.2613 1.69328 37.813 4.19778 38.4501 6.62326C39.0873 9.04874 41.5694 10.4717 44.0505 10.1071C47.8511 9.54855 51.7191 9.52689 55.5402 10.0491C60.8642 10.7766 65.9928 12.5457 70.6331 15.2552C75.2735 17.9648 79.3347 21.5619 82.5849 25.841C84.9175 28.9121 86.7997 32.2913 88.1811 35.8758C89.083 38.2158 91.5421 39.6781 93.9676 39.0409Z" :fill="accent"/>
    </svg>
  </div>
  <div class="main-part" id="mainPart">
    <header class="chapter header mb-12">
      <div class="container mx-auto">
        <div class="section mx-6 py-6 flex md:mx-24">
          <a href="#" class="name text-3xl text-neutral-900">Valentine</a>
          <div class="dropdown-menu group ml-auto my-auto relative">
            <button class="menu" id="menu-button">
              <svg width="25" height="21" viewBox="0 0 25 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect width="25" height="3" rx="2" :fill="accent"/>
              <rect y="8" width="25" height="3" rx="2" :fill="accent"/>
              <rect y="16" width="25" height="3" rx="2" :fill="accent"/>
              </svg>
            </button>
            <div class="dropdown-menu-content hidden pt-1 absolute right-0 ">
              <ul class="list-none text-lg space-y-3 p-6 accent text-neutral-50 rounded-md text-right accent-bg">
                <!-- <li><a href="#" class="footer-link hover:underline decoration-dashed underline-offset-4">О нас</a></li> -->
                <li><a href="https://t.me/SValentines_bot" class="footer-link hover:underline decoration-dashed underline-offset-4">Создать валентинку</a></li>
                <li><a href="https://www.buymeacoffee.com/serpant1ne" class="footer-link hover:underline decoration-dashed underline-offset-4">Поддержать проект</a></li>
              </ul>
            </div>
          </div>
          
        </div>
      </div>
      
    </header>
    <main class="chapter main mb-16">
      <div class="container mx-auto">
        <div class="section mx-6 text-neutral-900 md:mx-24">
          <h1 class="text-2xl mb-12">Эта валентинка предназначена для <span class="name">{{receiverName}}</span></h1>

          <div class="main-text relative flex mb-8">
            <svg width="71" height="61" viewBox="0 0 71 61" fill="none" xmlns="http://www.w3.org/2000/svg" class="absolute heart blur-sm h-12 -rotate-34 w-12">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M5.47839 30.5199L10.4697 35.5113L10.4697 35.5113L35.4264 60.468L35.4264 60.468L60.3831 35.5113L65.3745 30.52C72.2661 23.6284 72.2661 12.4549 65.3745 5.56327C58.4829 -1.32833 47.3093 -1.32833 40.4177 5.56327L35.4264 10.5546L30.4351 5.56324C23.5435 -1.32837 12.37 -1.32837 5.47839 5.56324C-1.41322 12.4548 -1.41322 23.6283 5.47839 30.5199Z" :fill="accent"/>
            </svg>
            <!-- <img src="./img/Heart.svg" alt="" class="absolute heart blur-sm h-10 -rotate-34 fill-blue-300"> -->
            <p class="text w-60 mx-auto text-xl my-4">{{mainText}}</p>
            <!-- <img src="./img/Heart.svg" alt="" class="absolute heart blur-sm h-10 rotate-45 bottom-0 right-0"> -->
            <svg width="71" height="61" viewBox="0 0 71 61" fill="none" xmlns="http://www.w3.org/2000/svg" class="absolute heart blur-sm h-12 w-12 rotate-45 bottom-0 right-0">
            <path fill-rule="evenodd" clip-rule="evenodd" d="M5.47839 30.5199L10.4697 35.5113L10.4697 35.5113L35.4264 60.468L35.4264 60.468L60.3831 35.5113L65.3745 30.52C72.2661 23.6284 72.2661 12.4549 65.3745 5.56327C58.4829 -1.32833 47.3093 -1.32833 40.4177 5.56327L35.4264 10.5546L30.4351 5.56324C23.5435 -1.32837 12.37 -1.32837 5.47839 5.56324C-1.41322 12.4548 -1.41322 23.6283 5.47839 30.5199Z" :fill="accent"/>
            </svg>
          </div>

          <div class="sender ml-auto mr-8 w-max text-xl">
            <span>От: <span class="name">{{senderName}}</span></span>
            </div>
        </div>
      </div>
    </main>
    <footer class="chapter footer  text-neutral-50 accent-bg" id="footer">
      <div class="container mx-auto">
        <div class="section mx-6 py-6 md:mx-24">
          <ul class="list-none text-lg space-y-3">
            <li><a href="#" class="text-2xl logo">Valentine</a></li>
            <!-- <li><a href="#" class="footer-link hover:underline decoration-dashed underline-offset-4">О нас</a></li> -->
            <li><a href="https://t.me/SValentines_bot" class="footer-link hover:underline decoration-dashed underline-offset-4">Создать валентинку</a></li>
            <li><a href="https://www.buymeacoffee.com/serpant1ne" class="footer-link hover:underline decoration-dashed underline-offset-4">Поддержать проект</a></li>
          </ul>
        </div>
      </div>
    </footer>
  </div>
  

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
  
  .chapter{
    transition: opacity .5s ease-in-out;
    opacity: v-bind(mainOpacity);
  }

  .dropdown-menu:hover > .dropdown-menu-content {
    display: block;
  }

  .dropdown-menu:active > .dropdown-menu-content {
    display: block;
  }

  .accent-bg{
    background-color: v-bind(accent);
  }
  
</style>

