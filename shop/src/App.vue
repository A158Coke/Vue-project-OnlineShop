<router-view>Productos</router-view>
<template>
  <div id="app">
    <div id="header">
      <div id="nav">
        <h1 id="logo-header">
          <router-link to="/"><img id="logo" src="../img/IC-logo.png" alt="?"></router-link>
        </h1>
        <div class="search">
          <input type="search" v-model="search" @keyup.enter="SearchProduct()" placeholder="Looking for something?">
        </div>
        <div class="cloud">
          <div class="snow">
            <span style="--i:11"></span>
            <span style="--i:12"></span>
            <span style="--i:15"></span>
            <span style="--i:17"></span>
            <span style="--i:18"></span>
            <span style="--i:13"></span>
            <span style="--i:14"></span>
            <span style="--i:19"></span>
            <span style="--i:20"></span>
            <span style="--i:16"></span>
            <span style="--i:10"></span>
            <span style="--i:7"></span>
            <span style="--i:8"></span>
            <span style="--i:21"></span>
            <span style="--i:22"></span>
            <span style="--i:24"></span>
            <span style="--i:23"></span>
          </div>
        </div>
        <nav>
          <ul>

            <li class="category-menu">
              <button class="dropdown-btn"><router-link to="/About">About us</router-link></button>
              <button class="dropdown-btn"><router-link to="/Productos">Products</router-link></button>
            </li>
            <li>
              <router-link to="/Cart/:id"><img id="log" src="../img/cart.png" alt="?"></router-link>
            </li>
            <li>
              <router-link to="/log"><img id="log" src="../img/log123.png" alt="?"></router-link>
            </li>
          </ul>
        </nav>
      </div>
    </div>
    <transition appear name="animateanimated router-animation" enter-active-class="animatefadeInUp">
      <router-view :productos="filteredProductos" />
    </transition>
  </div>
</template>

<script>
import axios from "axios";
//export default entender como un import de router(podemos encontrar en el router.js)
export default {
  //Inicializar los variables 
  data() {
    return {
      search: "",
      Productos: [],
      selectedCategory: "",
      categories: [],
      map: null, // 声明 map 变量并初始化为 null
    };
  },


  //Metodos
  methods: {
    //Dirigir al vista Result y mostrar los resultado allí
    SearchProduct() {
      this.$router.push({
        name: "Result",
        params: { search: this.search },
      });
    },
  },
};
</script>


<style>
@import "animate.css";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  color: #fff;
  padding: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  align-items: center;
  font-size: 20px;
  height: 10%;
  background-image: linear-gradient(125deg, rgb(31, 167, 167), #23b08d, #adadad, pink);
  background-size: 400%;
  animation: bgmove 20s infinite;
}

@keyframes bgmove {
  0% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
}

.cloud {
  position: relative;
  width: 110px;
  height: 30px;
  background: white;
  border-radius: 100px;
}

.cloud::before {
  content: '';
  position: absolute;
  width: 30px;
  height: 30px;
  background: white;
  border-radius: 50%;
  box-shadow: 40px 0 0 20px white;
  left: 10px;
  top: -20px;
}

.snow {
  position: relative;
  display: flex;
  z-index: 1;
}

.snow span {
  position: relative;
  width: 3px;
  height: 3px;
  background: white;
  margin: 0 2px;
  border-radius: 50px;
  animation: snowing 5s linear infinite;
  animation-duration: calc(15s / var(--i));
}

@keyframes snowing {
  0% {
    transform: translateY(0px);
  }

  70% {
    transform: translateY(100px) scale(1);
  }

  100% {
    transform: translateY(100px) scale(0);
  }
}

nav ul {
  list-style: none;
  margin: 0;
  padding: 0;
  display: flex;


}

.search input {
  width: 400px;
  height: 45px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 20px;
  padding: 10px;

}

#logo {
  width: 4rem;
  border-radius: 60%;
}

#log {
  width: 2rem;
  border-radius: 60%;
}

nav li {
  font-size: 1rem;
  margin: 0 10px -20px;
}



nav a {
  color: #e5dfdf;
  text-decoration: none;
}

body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

* {
  box-sizing: border-box;
}

#logo-header {
  margin-left: 5%;
  text-decoration: none;
  font-style: italic;
}

.search {
  width: 300;
  height: 100%;
  border-color: aqua;
  border-width: 10px;
}

a:visited {
  color: white;
}

a:link {
  color: white;
}

.category-menu {
  position: relative;
  display: inline-block;
}

.dropdown-btn {
  background-color: transparent;
  color: #fff;
  padding: 10px 20px;
  border: none;
  cursor: pointer;
  font-family: 'Montserrat', sans-serif;
  font-size: 3vh;
}

.dropdown-btn:hover {
  background-color: rgba(213, 56, 56, 0.793);
  border-radius: 20px;
}


.dropdown-content a {
  color: #333;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

.dropdown-content a:hover {
  background-color: #ddd;
}

.category-menu:hover .dropdown-content {
  display: block;
}

/* @media screen and (max-width: 600px) {

  .search input {
    width: 100%;
  }

  #nav {
    font-size: 16px;
  }

  #logo-header {
    margin-left: 2%;
    font-size: 1rem;
  }

  nav li {
    font-size: 0.8rem;
  }

  #nav {
    justify-content: center;
  }

  #logo-header {
    display: none;
  }

  nav li {
    margin: 0;
  }

  nav ul {
    flex-direction: column;
  }

  .category-menu {
    display: none;
  }

  .search input {
    margin-bottom: 10px;
  } */
</style>