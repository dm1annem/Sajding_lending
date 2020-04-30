<template>
    <div class="sajding-nav">
        <div class="container sajding-nav-content">
                    
            <nav class="nav">
                <ul>
                </ul>
            </nav>

        </div>
       
    </div>
</template>

<script>
export default {
    name: 'sajding-nav',
    data(){
  
    },
}
</script>

<style>
.sajding-nav {
    width: 100%;
    background-color: var(--nav-color);
}
.sajding-nav-content {
    grid-template-columns: 1fr 100vh 1fr;
}


</style>