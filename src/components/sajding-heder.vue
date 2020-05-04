<template>
    <div class="sajding-heder">
        <div class="sajding-heder-content" v-bind:style="styleContent">
            <div class="heder-logo" v-bind:style="styleLogo">
                <img :src=" require('../assets/img/LOGO-SAYDING.png')"  alt="Логотип" title="САЙДИНГ-БРЯНСК"> 
                <p> Из хедера:  {{ device }} по мобилке {{ av.tb_mb }} </p>
            </div>
            
            <div v-if="show" class="heder-icons">
               
                <div class="heder-icon-1">
                    <img :src="require('../assets/img/icon-bilder.png')"> 
                    <span>выезд замерщика</span>
                </div>
                <div class="heder-icon-2">
                    <img :src="require('../assets/img/icon-dostavka.png')"> 
                    <span>бережная доставка</span>
                </div>
                <div class="heder-icon-3">
                    <img :src="require('../assets/img/icon-home-on-hend.png')"> 
                    <span>професиональный монтаж</span>
                </div>
                 
                
                
            </div>

            <div class="fone-in-heder" :style="styleFone">
                <span>+7 930-820-02-25</span> 
                <span>+7(4832)30-02-25</span> 
                <a>
                    <button>Позвонить</button>
                </a>
            </div>
              
        </div>
       
    </div>
    
</template>


<script>
export default {
    name: 'sajding-heder',
    props: [
        'device',
        'av'
    ],
    data(){
        return{
            width: null,
            show: null,
            styleContent: {},
            styleLogo: {},
            styleFone: {}
        }
    },

    methods: {
        updateWidth() {
            this.width = window.innerWidth;
        },
     },

    watch: {
        width() {
            if (this.width > 970) {
                this.show = true
                this.styleContent.gridTemplateColumns = '1fr 1fr 1fr';
                this.styleLogo.justifyItems =  'left';
                this.styleFone.justifyItems = 'end';
            }
            else {
            this.show = false;
            this.styleContent.gridTemplateColumns = '1fr';
            this.styleLogo.justifyItems =  'center';
            this.styleFone.justifyItems = 'center';
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
.sajding-heder {
    display: grid;
    margin-top: 10px;
    
}
.sajding-heder-content {
    display: grid;
    
    margin: 0 50px;
}

.heder-logo{
    display: grid;
    
}

.heder-icons{
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    align-content: start;
    font-size: 12px;
}

.heder-icon-1, .heder-icon-2, .heder-icon-3{
    display: grid;
    justify-items: center;
}
.fone-in-heder {
    display: grid;
    align-content: flex-start;

}
.fone-in-heder button{
    display: grid;
    background: transparent;
    cursor: pointer;
    color: var(--nav-color);
    border: 2px solid var(--nav-color);
    border-radius: 20px;
    width: 130px;
}
.fone-in-heder span{
    font-size: 16px;
}
</style>