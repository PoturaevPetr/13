<template>
        <div class="container page">
            <div class="row">
                <div class="title">
                    <h4 class="col-6 offset-3 mt-5">One app, all things money</h4>
                    <br>
                    <p class="col-6 offset-3">Open a free account in minutes right from your phone, and make your money go further</p>
                </div>
                <div class="col-5 offset-7">
                    <button class="btn btn-primary" @click="openRegister">Get started &#8594;</button>
                </div>
            </div>
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
                                <button class="btn btn-primary" @click="openRegister">Registration</button>
                            </form>
                        </div>
                    </div>
                </div>
            </regform>
        </div>
</template>

<script>
import regform from "@/components/RegForm.vue"
export default {
    components: {
        regform
    },
    data() {
        return {
            register: false,
        }
    },
    methods: {
        openRegister() {
            if (this.register == false) {
                this.register = true;
            } else {
                this.register = false;
            }
            
        }
    }
};
</script>


<style scoped>
.title {
    margin-top: 12vh;
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
h4 {
    font: normal normal bold 8.9vh/10.2vh Poppins;
    text-align: center;
}
p {
    text-align: center;
    font: normal normal normal 2.04vh/2.5vh Poppins;
    letter-spacing: 0px;
    color: #007DFB;
    opacity: 1;
}
button {
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
.page {
    z-index: 0;
}
</style>