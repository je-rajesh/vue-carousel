<template>
    <!-- <div data-flickity='{"cellAlign":"left","contain":true,"wrapAround":true}'> -->
    <div>
        <slot></slot>
    </div>
</template>

<script>
    import Flickity from 'flickity';
    import 'flickity/dist/flickity.min.css';

    export default { 
        
        props: {
            wraparound: {default: true},
            autoplay: {default: false},
            contain: { default: false },
            cellAlign: {default: 'left'},
            imagesLoaded: {default: false},
            percentPosition: {default: false},
            draggable: {default: true}
        },

        mounted() {
            new Flickity(this.$el, {
                cellAlign: this.cellAlign,
                contain: this.contain, 
                autoPlay: this.autoplay,
                wrapAround: this.wraparound,
                imagesLoaded: this.imagesLoaded,
                percentPosition: this.percentPosition,
                draggable: this.draggable,

            });
        }
    }
</script>
