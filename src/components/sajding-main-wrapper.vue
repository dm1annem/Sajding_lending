<template>
    <div class="sajding-main-wrapper"> 
    <p>Из главной обёртки: {{ currentDevise }} мобилка{{ activeVisibiliti.dt_tb }} </p>
    <sajding-heder
    :device="currentDevise"
    :av="activeVisibiliti"
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
            breakpoints: {
                maxMobile: 576,
                maxTablet: 970,

            },
            activeVisibiliti: {
                // зоны видимости с ограничением по ширине экранов:
                dt: false, //десктопы
                tb: false, //планщеты
                mb: false,// мобильные
                dt_tb: false, //на десктопах и планшетах
                tb_mb: false, //планшеты и мобильные
            },
            
            
        }
    },
    methods: {
        updateWidth() {
            this.screenWidth = window.innerWidth;
        },
    },

    watch: {
        screenWidth() {
            //определяем тип устройства по ширине экрана
            if (this.screenWidth <= this.breakpoints.maxMobile) {
                this.currentDevise = 'modile';
                this.activeVisibiliti.dt = false;
                this.activeVisibiliti.tb = false;
                this.activeVisibiliti.mb = true;
                this.activeVisibiliti.dt_tb = false;
                this.activeVisibiliti.tb_mb = true;
            }
            else if (this.breakpoints.maxMobile < this.screenWidth && this.screenWidth <= this.breakpoints.maxTablet) {
                this.currentDevise = 'tablet';
                this.activeVisibiliti.dt = false;
                this.activeVisibiliti.tb = true;
                this.activeVisibiliti.mb = false;
                this.activeVisibiliti.dt_tb = true;
                this.activeVisibiliti.tb_mb = true;
            }
            else if (this.screenWidth > this.breakpoints.maxTablet) {
                this.currentDevise = 'desktop';
                this.activeVisibiliti.dt = true;
                this.activeVisibiliti.tb = false;
                this.activeVisibiliti.mb = false;
                this.activeVisibiliti.dt_tb = true;
                this.activeVisibiliti.tb_mb = false;
            }
            // if (this.screenWidth < this.maxMobile) {
            //     this.mb = true;
            // }
        },
        // activeVisibiliti() {
        //     if (this.screenWidth < this.maxMobile) {
        //         this.activeVisibiliti.mb = true;
        //     }

        // },
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