<template>
<div v-if="open">
    
    <div class="regform">
        <slot></slot>
    </div>
</div>

</template>


<script>
export default {
    props: ['open'],


}
</script>

<style scoped>

.regform {
    position: fixed;
    background: white;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;


    overflow-y: auto;
    -ms-overflow-style: none;
    scrollbar-width: none;


    box-shadow: 0px 0px 10px #ACACAC63;
    border: 1px solid #FFFFFF;
}
.regform::-webkit-scrollbar {
    width: 0;
    height: 0;
}

</style>