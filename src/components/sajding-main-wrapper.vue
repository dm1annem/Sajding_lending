<template>
    <div class="sajding-main-wrapper"> 
    
    <sajding-heder/>
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
            
            
        }
    },
    
}
</script>

<style>
.sajding-main-wrapper{
    width: 100%;
}
.container {
    display: grid;
    justify-content: stretch;
    /*grid-template-rows: 1fr;
    justify-self: centr;
    width: 100%;*/
    max-width: 1200px;
}

</style>