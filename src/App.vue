<template>
    <div id="app">
        <a-scene embedded arjs>
            <a-marker preset="hiro">
                <a-box position='0 0.5 0' material='color: yellow;'></a-box>
            </a-marker>
            <a-entity camera></a-entity>
        </a-scene>
    </div>
</template>

<script>
    // import anime from 'animejs';

    export default {
        name: 'app',
        components: {},
        mounted() {

        },
    }
</script>

<style>
    #app{position: absolute;left: 0;top:0;right:0;bottom:0;}
</style>
