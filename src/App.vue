<template>
    <div id="app">
        <MyHeader />  
        <div class="app-content">
            <MyFilter />
            <MyCatalog />
        </div>
    </div>
</template>

<script>
import MyHeader from './views/MyHeader.vue'
import MyFilter from './views/MyFilter.vue'
import MyCatalog from './views/MyCatalog.vue'

export default {
    name: 'App',
    components: {
        MyHeader,
        MyFilter,
        MyCatalog,
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=PT+Sans:ital,wght@0,400;0,700;1,400;1,700&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

#app {
    padding: 0 100px;
}

.app-content {
    display: flex;
}
</style>