<template>
    <div id="app">
        <a-scene>
            <a-assets>
                <img id="city" crossorigin="anonymous" src="https://cdn.aframe.io/360-image-gallery-boilerplate/img/city.jpg">

                <!--<a-asset-item id="car" src="/pony_cartoon/scene.gltf"></a-asset-item>-->

            </a-assets>

            <!-- 360-degree image. -->
            <a-sky id="image-360" radius="10" src="#city"></a-sky>


            <!--<a-entity gltf-model="#car"></a-entity>-->

            <a-entity gltf-model="url(/pony_cartoon/scene.gltf)" scale="0.001 0.001 0.001"></a-entity>


            <a-light color="yellow" position="-1 1 0"></a-light>


            <a-camera id="camera" position="1 1.6 0" fov="80" camera-anime="message:ssss dddd"

            ></a-camera>

            <!-- Camera + cursor. -->
            <!--<a-entity camera look-controls wasd-controls position="1 1.6 0"-->
                      <!--animation="property: position; to: 1 2.2 0; dur: 1500; easing: linear; dir: alternate; loop: true;"-->
            <!--&gt;-->
                <!--<a-cursor id="cursor"-->
                          <!--animation__click="property: scale; startEvents: click; from: 0.1 0.1 0.1; to: 1 1 1; dur: 150"-->
                          <!--animation__fusing="property: fusing; startEvents: fusing; from: 1 1 1; to: 0.1 0.1 0.1; dur: 1500"-->
                          <!--event-set__1="_event: mouseenter; color: springgreen"-->
                          <!--event-set__2="_event: mouseleave; color: black"-->
                          <!--fuse="true"-->
                          <!--raycaster="objects: .link"></a-cursor>-->
            <!--</a-entity>-->
        </a-scene>
    </div>
</template>

<script>
    // import anime from 'animejs';

    export default {
        name: 'app',
        components: {},
        mounted() {
            // const camera = document.getElementById('camera');
            // AFRAME.ANIME({
            //     targets: camera,
            //     position: '0 0 0',
            //     direction: 'alternate',
            //     loop: true,
            //     duration: 1800,
            //     easing: 'linear'
            // });


            AFRAME.registerComponent('camera-anime', {
                schema: {
                    event: {type: 'string', default: ''},
                    message: {type: 'string', default: 'Hello, World!'}
                },
                init: function () {
                    // console.log(this.data.message);

                    var data = this.data;  // Component property values.
                    var el = this.el;  // Reference to the component's entity.


                    el.setAttribute('animation', {
                        property: 'position',
                        dir: 'alternate',
                        dur: 1500,
                        to: '1 2.2 0',
                        loop: true,
                        easing: 'linear',
                    });
                },
                update: function () {
                    var data = this.data;  // Component property values.
                    var el = this.el;  // Reference to the component's entity.

                    if (data.event) {
                        // This will log the `message` when the entity emits the `event`.
                        el.addEventListener(data.event, function () {
                            console.log(data.message);
                        });
                    } else {
                        // `event` not specified, just log the message.
                        console.log(data.message);
                    }
                },
                tick: function () {},
                remove: function () {},
                pause: function () {},
                play: function () {}
            });
        },
    }
</script>

<style>

</style>
