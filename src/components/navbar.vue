<template>
  <div>
    <nav class="navbar navbar-expand-lg ">
      <div class="container-fluid">
        <a class="navbar-brand" href="#"><h4>Company</h4></a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <a class="nav-link" aria-current="page" href="#">Products</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Prices</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="#">Security</a>
            </li>
            <li class="nav-item">
              <a class="nav-link" href="" @click.prevent="openResources()">Resources <img :src="getFlag" alt=""></a>
            </li>
          </ul>
          <form>
            <button class="butsing btn btn-light" @click.prevent="openRegister">Log in</button>
            <a class="language" @click.prevent="openLang">{{currentLang}} <img :src="getFlag" alt=""></a>
            <a class="choisSearch" @click.prevent="openSearch"><img class="imgsearch" src="../assets/flags/Search.svg" alt=""></a>
          </form>
        </div>
      </div>
    </nav>
    <div class="search input-group" v-if="search">
      <input type="text" class="searchinput form-control" placeholder="Search">
    </div>
    <droplist id="resources" :open="resources">
      <div>
        <div class="container droplist">
          <div class="row mb-3 mt-3">
            <div class="col-6">
              <h5>About</h5>
              <p>We aim to continuously refine our services in highly dynamic industry.</p> 
            </div>
            <div class="col-6">
              <h5>Careers</h5> 
              <p>Come join our team and help us build the future.</p> 
            </div>
          </div>
          <br><br>
          <div class="row mb-3">
            <div class="col-6">
              <h5>Support</h5>
              <p>Answers to FAQs and how to contact our customer service team.</p>  
            </div>
            <div class="col-6">
              <h5>Blog</h5> 
              <p>Aroduct announcements, company updates, and industry perspectives.</p> 
            </div>
          </div>
        </div>
      </div>
    </droplist>
    <regform :open="register">
      <div class="mask"></div>
      <div class="container">
          <div class="row">
              <div class="col-6">
                  <h4>Company</h4>
                  <h5>Registration form</h5>
                  <form>
                      <div class="form-group pt-1 pb-1">
                        <input type="text" class="form-control" id="exampleInputName" aria-describedby="NameHelp" placeholder="Name">
                      </div>
                      <div class="form-group pt-1 pb-1">
                        <input type="text" class="form-control" id="exampleInputCountry" aria-describedby="CountryHelp" placeholder="Country">
                      </div>
                      <div class="form-group pt-1 pb-1">
                        <input type="email" class="form-control" id="exampleInputEmail" aria-describedby="emailHelp" placeholder="Email">
                      </div>
                      <div class="form-group pt-1 pb-2">
                        <input type="phone" class="form-control" id="exampleInputPhone" placeholder="Phone">
                      </div>
                      <button type="submit" class="regbut btn btn-primary" @click="openRegister">Registration</button>
                  </form>
              </div>
          </div>
      </div>
    </regform>
    <div class="lang" v-if="language">
      <li class="current">{{currentLang}} <img src="../assets/flags/check.svg" alt=""> </li>
      <li class="list" v-for="(l, ind) in lang" :key="ind" @click="choisLang(ind)">{{l}}</li>
    </div>
  </div>
</template>


<script>
import droplist from '@/components/drop.vue'
import regform from '@/components/RegForm.vue'

export default {
  components: {
    droplist,
    regform,

  },
  data() {
    return {
      resources: false,
      flag: "../assets/flags/arrow.png",
      register: false,
      search: false,
      language: false,
      currentLang: "",
      lang: [
        'English',
        'Русский',
        'Text',
        'Text',
        'Text',
        'Text',
        'Text',
        'Text',
        'Text',
        'Text',
        'Text',
        'Text'
      ]
    }
  },

  
  methods: {
    openSearch() {
      if (this.search == false) {
        this.search = true;
      } else {
        this.search = false;
      }
    },
    openRegister() {
      if (this.register == false) {
        this.register = true;

      } else {
        this.register = false;
        }
    },
    openResources() {
      if (this.resources == false) {
        this.resources = true;

      } else {
        this.resources = false;
        }
    },
    openLang() {
      if (this.language == false) {
        this.language = true;

      } else {
        this.language = false;
        }
    },
    choisLang(ind) {
      this.currentLang = this.lang[ind];
      document.addEventListener('click', e => console.log(e.target))

    },
    firstLang() {
      this.currentLang = this.lang[0];
    }
  },
  created() {
    this.firstLang();
  },
  computed: {
    getFlag() {
      if (this.resources == true) {
        return require('../assets/flags/arrow_top.png');
      } else {
        return require('../assets/flags/arrow.png');
      }  
    },
  },
};
</script>


<style scoped>
li {
  list-style-type: none;
}
.language {
  text-align: left;
  font: normal normal normal 1.9vh/1.6vw Poppins Regular;
  letter-spacing: 0px;
  color: #707070;
  opacity: 1;
  text-decoration: none;
  margin: 0 1.5vw;
}  
.lang {
  position: fixed;
  right: 4vw;
  width: 9.5vw;
  height: 31.9vh;
  background: rgba(65, 63, 63, 0.1);
  border: 1px solid #FFFFFF73;
  border-radius: 42px;
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
}
.list{
  color: rgb(255, 254, 255);
  text-align: center;
}
.list:active {
  color: blue;
}
.current {
  color: white;
  text-align: center;
}
.current img {
  filter: brightness(0) invert(1);
}
.choisSearch {
  margin: 0 1.5vw;
}
.imgsearch:hover {
  filter: brightness(0%);
}

.search {
  position: fixed;
  right: 1.5vw;
  height: 5.1vh;
  width: 19.2vw;
  border-radius: 52px;
  opacity: 1;  
}

.searchinput {
  height: 5.1vh;
  width: 19.2vw;
  border-radius: 52px;
  box-shadow: 0px 0px 10px #007DFB;
  background: white url("../assets/flags/Search.svg") no-repeat 95%;
}

.searchinput:focus {
  box-shadow: 0px 0px 10px #00000033;
  border: 1px solid #007DFB;
  background: white url("../assets/flags/Search.svg") no-repeat 95%;
}


.mask {
  position: fixed;
  z-index: -1;
  height: 100vh;
  width: 100vw;
  background: transparent url("../assets/background/fon.png") no-repeat;
  background-size: cover;
  mask: url("../assets/background/fon_contr.png") no-repeat right;
}
.butsing {
  background-color:#FFFFFF;
  border-radius: 28px;
  height: 5.1vh;
  width: 6.8vw;
  margin: 0 1.5vw;
}
.regbut {
  text-align: center;
  font: normal normal normal 2.78vh/3.3vh Libre Franklin;
  letter-spacing: 0px;
  color: #FFFFFF;
  opacity: 1;
  width: 30.7vh;
  height: 11.4vh;
  border-radius: 62px;
}
input {
  background: rgba(243, 244, 246, 1) 0% 0% no-repeat padding-box;
  border-radius: 52px;
  height: 7.4vh;
  opacity: 1;
}

nav {
  height: 100px;
}
h4 {
  text-align: left;
  font: normal normal 600 3.2vh/4.9vh Poppins SemiBold;
  letter-spacing: 0px;  
  color: #000000;
  opacity: 1; 
}
a, h5 {
  text-align: center;
  font: normal normal normal 2.3vh/3.5vh Poppins Regular;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
  cursor: pointer;
}
h5 {
  text-align: left;
}
.droplist h5:hover {
  color: rgba(82, 113, 243, 1);
  
}


p {
  text-align: left;
  font: normal normal normal 1.6vh/2.5vh Poppins Regular;
  letter-spacing: 0px;
  color: #000000;
  opacity: 1;
}
</style>
