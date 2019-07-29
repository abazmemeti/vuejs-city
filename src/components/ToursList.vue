<template>
    <transition-group name="fade" tag="section">
        <div :key="tours.id" v-for="tours in tourData">
            <Tour :tour="tours" @del-tour="deleteCity" />
        </div>
        </transition-group>
</template>

<script>
import Tour from './Tour.vue';
import { tourData } from './tourData';

export default {
    name: 'ToursList',
    data() {
        return {
           tourData
        }
    },
    components: {
        Tour
    },
    methods: {
        deleteCity(id) {
            this.tourData = this.tourData.filter(tour => tour.id !== id)
        }
    }
}
</script>

<style scoped>
    section {
        width: 85vw;
        margin: 1.5rem auto;
        display: grid;
        grid-template-columns: 1fr;
        grid-gap: 1rem;
    }
    @media screen and (min-width: 768px) {
        section {
            grid-template-columns: 1fr 1fr;
        }
    }
    @media screen and (min-width: 912px) {
        section {
            grid-template-columns: repeat(3, 1fr);
        }
    }
    @media screen and (min-width: 1140px) {
        section {
            grid-template-columns: repeat(4, 1fr);
        }
    }


.fade-enter-active {
  -webkit-transition: all 0.4s;
  transition: all 0.4s;
  -webkit-transition-delay: 0.52s;
  transition-delay: 0.52s;
}

.fade-leave-active {
  -webkit-transition: all 0.4s;
  transition: all 0.4s;
}

.fade-enter, .fade-leave-to {
  opacity: 0
}
</style>