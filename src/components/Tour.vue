<template>
    <div>
        <article>
            <div class="img">
                <img :src='"img/"+ tour.img' />
                <i @click="$emit('del-tour', tour.id)" class="fas fa-window-close" />
            </div>
            <div class="info">
                <h3>{{ tour.city }}</h3>
                <h4>{{ tour.name }}</h4>
                <h5>Info 
                    <span @click="show=!show"><i :class="{'fas fa-caret-square-down':!show, 'fas fa-caret-square-up':show}" /></span>
                </h5>
            </div>
        </article>
        <transition name="fade">
            <p v-if="show">{{ tour.info }}</p>
        </transition>
    </div>
</template>

<script>
export default {
    name: 'Tour',
    props: ['tour'],
    data() {
        return {
            show: false
        } 
    }
}
</script>

<style scoped>
    article {
        background-color: #eee;
        border-top-left-radius: 0.8rem;
        border-top-right-radius: 0.8rem;
        overflow: hidden;
    }
    .img {
        position: relative;
    }
    img {
        width: 100%;
    }
    .fa-window-close {
        position: absolute;
        color: #42b983;
        display: block;
        top: 5%;
        right: 4%;
        font-size: 1.5rem;
        cursor: pointer;
        transition: all 0.3s linear;
        opacity: 0;
    }
    article:hover i.fa-window-close {
        opacity: 1;
    }
    .info {
        padding: 0.6rem 0.6rem 0.2rem;
    }
    h3 {
        text-transform: uppercase;
        color:#42b983;
        padding-bottom: 0.4rem;
    }
    h4 {
        text-transform: capitalize;
        color:#333;
        padding-bottom: 0.7rem;
    }
    h5, p {
        color:#333;
        padding-bottom: 0.4rem;
    }
    p {
        background-color: #eee;
        padding: 0 0.6rem 0.6rem;
    }
    h5 span i {
        color: #42b983;
        font-size: 1.2rem;
        cursor: pointer;
    }
    .fade-enter-active, .fade-leave-active {
        transition: all .5s linear;
    }
    .fade-enter, .fade-leave-to {
        opacity: 0;
    }
</style>