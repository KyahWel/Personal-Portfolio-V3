<template>
  <div> 
   <transition name="fade">
    <div v-if="toggle_theme" class="main darkTheme" >
      <div class="menu menuDark" >
        <a>Home</a>
        <a>Techstack</a>
        <a>Projects</a>
        <a @click="toggleTheme()"><i class="fa-solid fa-moon"></i></a>
      </div>
      <a-layout-content><Home /></a-layout-content>
      <a-layout-content><Projects /></a-layout-content>
      <a-layout-content><Techstack /></a-layout-content>  
    </div>
    <div v-else class="main lightTheme" >
      <div class="menu menuLight" >
        <a>Home</a>
        <a>Techstack</a>
        <a>Projects</a>
        <a @click="toggle_theme = !toggle_theme"><i class="fa-regular fa-moon"></i></a>
      </div>
      <a-layout-content><Home /></a-layout-content>
      <a-layout-content><Projects /></a-layout-content>
      <a-layout-content><Techstack /></a-layout-content>  
    </div>
  </transition>
  </div>
 
</template>

<script>
  export default {
    data(){
      return{
        toggle_theme: true
      }
    },
    head: {
    link: [
      {
        rel: "stylesheet",
        href: "https://fonts.googleapis.com/css2?family=Montserrat:wght@500&family=Quicksand:wght@300&family=Raleway:wght@700&display=swap",
      },
      {
        rel: "stylesheet",
        href: "https://fonts.googleapis.com/css2?family=Poppins:wght@100;800&display=swap",
      },
      {
        rel: "stylesheet",
        href: "https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.3.0/css/all.min.css",
      },
      ],
    },
    methods:{
      toggleTheme(){
        this.toggle_theme = !this.toggle_theme
      }
    }
  }
</script>

<style>
  .main{
    display: flex;
    flex-direction: column;
  }

  .menu{
    display:flex;
    justify-content: center;
    align-items: center;
    padding: 1.5em;
    gap: 2em;
    text-decoration: none;
    font-size: 1.2em;
    font-family: "Montserrat";
    text-transform: uppercase;
  }

  .menuLight a{
    transition: color 0.5s ease-in-out;
    color: #151618;
   
  }

  .menuDark a{
    transition: color 0.5s ease-in-out;
    color: #f5f5f5
  }

  .darkTheme{
    transition: background-color 0.5s ease-in-out;
    background:#151618 ;
    color: #f5f5f5
  }

  .lightTheme{
    transition: background-color 0.5s ease-in-out;
    background:#f5f5f5;
    color:  #151618
  }
</style>