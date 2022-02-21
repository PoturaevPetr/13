<template>
  <div id="app">
    <navbar/>
    <start-page/>
  </div>
</template>

<script>
import navbar from "@/components/navbar.vue"
import startPage from "@/components/StartPage.vue"
export default {
  components: {
    navbar,
    startPage,
  }
}
</script>

<style scoped>
@font-face {
    font-family: 'Poppins';
    src: url('./assets/fonts/Poppins-Bold.eot');
    src: local('Poppins Bold'), local('Poppins-Bold'),
        url('./assets/fonts/Poppins-Bold.eot?#iefix') format('embedded-opentype'),
        url('./assets/fonts/Poppins-Bold.woff2') format('woff2'),
        url('./assets/fonts/Poppins-Bold.woff') format('woff'),
        url('./assets/fonts/Poppins-Bold.ttf') format('truetype');
    font-weight: bold;
    font-style: normal;
}
@font-face {
    font-family: 'Libre Franklin';
    src: url('./assets/fonts/LibreFranklin-Regular.eot');
    src: local('LibreFranklin-Regular'),
        url('./assets/fonts/LibreFranklin-Regular.eot?#iefix') format('embedded-opentype'),
        url('./assets/fonts/LibreFranklin-Regular.woff2') format('woff2'),
        url('./assets/fonts/LibreFranklin-Regular.woff') format('woff'),
        url('./assets/fonts/LibreFranklin-Regular.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
}

@font-face {
    font-family: 'Poppins Regular';
    src: url('./assets/fonts/Poppins-Regular.eot');
    src: local('Poppins Regular'), local('Poppins-Regular'),
        url('./assets/fonts/Poppins-Regular.eot?#iefix') format('embedded-opentype'),
        url('./assets/fonts/Poppins-Regular.woff2') format('woff2'),
        url('./assets/fonts/Poppins-Regular.woff') format('woff'),
        url('./assets/fonts/Poppins-Regular.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
}

@font-face {
    font-family: 'Poppins SemiBold';
    src: url('./assets/fonts/Poppins-SemiBold.eot');
    src: local('Poppins SemiBold'), local('Poppins-SemiBold'),
        url('./assets/fonts/Poppins-SemiBold.eot?#iefix') format('embedded-opentype'),
        url('./assets/fonts/Poppins-SemiBold.woff2') format('woff2'),
        url('./assets/fonts/Poppins-SemiBold.woff') format('woff'),
        url('./assets/fonts/Poppins-SemiBold.ttf') format('truetype');
    font-weight: 600;
    font-style: normal;
}

#app {
  background: transparent url("./assets/background/fon.png") no-repeat;
  background-size: cover;
  height: 100vh;

}

</style>
