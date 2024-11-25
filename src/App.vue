<template>
    <div id="app">
        <MyHeader />   
    </div>
</template>

<script>
import MyHeader from './components/MyHeader.vue'

export default {
    name: 'App',
    components: {
        MyHeader
    }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');

* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
</style>