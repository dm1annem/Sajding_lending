<template>
    <div class="sajding-main-wrapper"> 
    <p>{{ msg }}</p>
    <sajding-nav/>
    
    </div>
</template>

<script>
import sajdingNav from './sajding-nav'

export default {
    name: 'sajding-main-wrapper',
    components: {
       sajdingNav, 
    },
    data() {
        return {
            msg: 'Я главная обёртка'
            
        }
    },
    
}
</script>

<style>

</style>