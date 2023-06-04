<template>
  <div class="home-page">
    <div class="swing-in-top-fwd">
      <div class="content-wrapper">
        <div class="text-wrapper">
          <p id="home-welcome-title">
            Store - IC <br />
            Smart Solutions for a Smarter Future
          </p>
          <p id="home-welcome-text">
            Discover the Latest in Smart Technology for a Smarter Living
            Experience
          </p>
        </div>
        <div class="image-wrapper">
          <img src="../../img/gif-home-page.gif" alt="Image Description" class="image-with-shadow" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
//export default entender como un import de router(podemos encontrar en el router.js)
export default {
  name: "Home",
};
</script>


<!-- CSS -->
<style>
.home-page {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  min-height: 100vh;
  padding: 20px;
  text-align: center;
  background-image: linear-gradient(125deg, rgb(204, 227, 102), #a762e3, #adadad, pink);
  background-size: 400%;
  animation: bgmove 20s infinite;
  background-position: 100%;
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

.content-wrapper {
  display: flex;
  align-items: center;
  max-width: 70rem;
  /* Set a maximum width for the content wrapper */
  margin-top: 5%;
  /* Center the content horizontally within the wrapper */
}

.text-wrapper {
  flex: 1;
  margin-right: 40px;
}

#map {
  float: right;
  height: 300px;
  width: 20%;
}

#home-welcome-title {
  padding-top: 5%;
  text-align: left;
  width: 100%;
  font-size: 3.2rem;
  font-weight: 200;
  font-style: normal;
  background: linear-gradient(45deg, red, blue, green);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
  font-family: "Montserrat", sans-serif;
}

#home-welcome-text {
  text-align: left;
  width: 64.5%;
  font-size: 1.3rem;
  font-weight: lighter;
  font-family: "Montserrat", sans-serif;
}

.map-wrapper {
  width: 100%;
}

#item-search {
  width: 40%;
  height: 50px;
  border: 1px solid #b12d2d;
  border-radius: 5px;
  padding: 0 20px;
  font-size: 1.2rem;
}

.image-with-shadow {
  /* Adjust the shadow properties as needed */
  filter: drop-shadow(0 0 10px rgba(0, 0, 0, 0.5));
  display: inline-block;
}

.swing-in-top-fwd {
  animation: swing-in-top-fwd 1.5s cubic-bezier(0.175, 0.885, 0.320, 1.275);
}

@keyframes swing-in-top-fwd {
  0% {
    -webkit-transform: rotateX(-100deg);
    transform: rotateX(-100deg);
    -webkit-transform-origin: top;
    transform-origin: top;
    opacity: 0;
  }

  100% {
    -webkit-transform: rotateX(0deg);
    transform: rotateX(0deg);
    -webkit-transform-origin: top;
    transform-origin: top;
    opacity: 1;
  }
}
</style>