<template>
    <div class="sajding-main-wrapper"> 
    <p>Из главной обёртки: {{ currentDevise }}</p>
    <sajding-heder
    :device="currentDevise"
    />
    <sajding-nav/>
    
    </div>
</template>

<script>
import sajdingNav from './sajding-nav'
import sajdingHeder from './sajding-heder'

export default {
    name: 'sajding-main-wrapper',
    components: {
        sajdingHeder,
        sajdingNav, 
    },
    data() {
        return {
            screenWidth: null,
            currentDevise: null,
            
            
        }
    },
    methods: {
        updateWidth() {
            this.screenWidth = window.innerWidth;
        },
    },

    watch: {
        screenWidth() {
            if (this.screenWidth <= 576) {
                this.currentDevise = 'modile'
            }
            else if (576 < this.screenWidth && this.screenWidth <= 970) {
                this.currentDevise = 'tablet'
            }
            else if (this.screenWidth > 970) {
                this.currentDevise = 'desktop'
            }
        }
    },

    created() {
    window.addEventListener('resize', this.updateWidth,);
    this.updateWidth();
    },
}
</script>

<style>
.sajding-main-wrapper{
    width: 100%;
}
.container {
    display: grid;
    max-width: 1220px;
    margin: 0 10px 0 10px;
    justify-self: center;
}

</style>