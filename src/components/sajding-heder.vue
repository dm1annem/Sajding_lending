<template>
    <div class="sajding-heder">
        <div class="container sajding-heder-content">
            <div>
                <img :src=" require('../assets/img/LOGO-SAYDING.png')"  alt="Логотип" title="САЙДИНГ-БРЯНСК"> 
            </div>
            
            

            <div class="fone-nav">
                <span>+7 930-820-02-25</span> 
                <span>+7(4832)30-02-25</span> 
            </div>
              
        </div>
       
    </div>
    
</template>


<script>
export default {
    name: 'sajding-heder',
    data(){
        

    },
}
</script>

<style>
.sajding-heder {
    display: grid;
    margin-top: 10px;
}
.sajding-heder-content {
    grid-template-columns: 1fr 100vh 1fr;
    justify-self: center;
}
.fone-in-heder {
    display: grid;
    justify-content: end;

}

</style>