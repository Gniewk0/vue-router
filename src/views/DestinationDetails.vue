<template>
<div>
    <section class="destinations">
        <h1>{{destination.name}}</h1>
        <div class="destination-details">
            <img :src="require(`@/assets/${destination.image}`)" 
            :alt='destination.name'>
            <p>{{destination.description}}</p>
        </div>
    </section>
    <section class="expiriences">
        <h2>Top experiences in {{ destination.name }}</h2>
        <div class="cards">
            <div 
            v-for="experience in destination.experiences" 
            :key="experience.slug" 
            class="card"
            >
                <!-- <img :src="require(`@/assets/${experience.image}`)" :alt="experience.name"> -->
            </div>
            <span class="card_text">
                {{ experience.slug }}
            </span>
        </div>
    </section>
</div>
</template>
<script>
import store from "../store.js"
export default {
    data(){
        return {}    
    },
    props: {
        slug: {
            type: String,
            required: true
        }
    },
    computed: {
        destination(){
            return store.destinations.find(
                destination => destination.slug === this.slug
            )
        }
    }
}
</script>
<style scoped>
    img {
        max-width: 600px;
        height: auto;
        width: 100%;
        max-height: 400px;
    }
    .destination-details {
        display: flex;
        justify-content: space-between;
    }
    p {
        margin: 0 40px;
        font-size: 20px;
        text-align: left;
    }
    .cards img {
        max-height: 200px;
    }
    .card {
        padding: 0 20px;
        position: relative;
    }
    .card_text {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        color: white;
        font-size: 25px;
        font-weight: bold;
        text-decoration: none;
    }
</style>