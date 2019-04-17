<template>
    <div id="app">
        <a-scene>
            <a-assets>
                <img id="boxTexture" src="https://lh3.googleusercontent.com/-MNA6LIRPLh8/AAAAAAAAAAI/AAAAAAAAAAA/ACevoQM9IrK31nP25dNhP0nRvnQ6tMd7Mw/s64-c-mo/photo.jpg">
                <img id="skyTexture" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/sechelt.jpg">
                <img id="groundTexture" src="https://cdn.aframe.io/a-painter/images/floor.jpg">
            </a-assets>

            <a-box src="#boxTexture"
                   position="0 2 -5"
                   rotation="0 45 45"
                   animation="property: position; to: 0 2.2 -5; dur: 1500; easing: linear; dir: alternate; loop: true;"
                   scale-on-mouseenter="to: 2.2 2.2 2.2"
            >

            </a-box>

            <a-sky src="#skyTexture"></a-sky>

            <a-plane src="#groundTexture" rotation="-90 0 0" width="30" height="30" repeat="10 10"></a-plane>

            <a-light type="ambient" color="#445451"></a-light>
            <a-light type="point" intensity="2" position="2 4 4"></a-light>


            <a-camera>
                <a-cursor></a-cursor>
            </a-camera>
        </a-scene>
    </div>
</template>

<script>
    import HelloWorld from './components/HelloWorld.vue'

    export default {
        name: 'app',
        components: {
            HelloWorld
        },
        mounted() {
            // AFRAME.registerComponent('scale-on-mouseenter', {
            //     schema: {
            //         to: {default: '2.5 2.5 2.5'}
            //     },
            //
            //     init: function () {
            //         var data = this.data;
            //         this.el.addEventListener('mouseenter', function () {
            //             this.setAttribute('scale', data.to);
            //         });
            //     }
            // });
        },
    }
</script>

<style>

</style>
