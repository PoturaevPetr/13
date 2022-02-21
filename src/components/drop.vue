<template>
    <div class="drop">
        <transition>
            <div class="front" v-if="open">
                <slot></slot>
            </div> 
        </transition>    
    </div>
</template>
 
<script>
export default {
    props: ['open'],
};
</script>

<style scoped>
.front {
    position: fixed;
    background-color: rgba(255, 255, 255, 0.7);
    top: 13.4vh;
    width: 44.4vw;
    
    left: calc(50vw - 44.4vw/2);
    padding: 20px;
    border-radius: 42px;
    overflow-y: auto;
    -ms-overflow-style: none;
    scrollbar-width: none;

    backdrop-filter: blur(17px);
    -webkit-backdrop-filter: blur(15px);
    box-shadow: 0px 0px 10px #ACACAC63;
    border: 1px solid #FFFFFF;
}
.front::-webkit-scrollbar {
    width: 0;
    height: 0;
}

</style>