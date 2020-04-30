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
    max-width: 1220px;
    margin: 0 10px 0 10px;
    justify-self: center;
}

</style>