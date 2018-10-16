<template>
    <div :id="elementHandle" :class="['owl-carousel', 'owl-theme', customClass]">
        <slot></slot>
    </div>
</template>
<script>
    import 'owl.carousel/dist/assets/owl.carousel.css';
    import 'owl.carousel/dist/assets/owl.theme.default.css';
    import 'owl.carousel';
    
    export default {
      name: 'VOwlCarousel',
      data: function(){
        return {
            elementHandle: 'carousel_' +  Math.random().toString(36).substring(2, 15) + Math.random().toString(36).substring(2, 15)
          }
      },
      props: {
          customClass: {
              default: ''
          },
        items : {
            default: 3
        },
        margin : {
            default: 0
        },
        loop : {
            default: false
        },
        center : {
            default: false
        },
        nav : {
            default: true
        },
        autoplay : {
            default: false
        },
        autoplaySpeed : {
            default: false
        },
        rewind : {
            default: true
        },
        mouseDrag : {
            default: true
        },
        touchDrag: {
            default: true
        },
        pullDrag: {
            default: true
        },
        freeDrag: {
            default: false
        },
        stagePadding: {
            default: 0
        },
        autoWidth: {
            default: false
        },
        autoHeight: {
            default: false
        },
        dots: {
            default: true
        },
        autoplayTimeout: {
            default: 5000
        },
        autoplayHoverPause: {
            default: false
        },
        responsive: {
            default: {}
        },
        dotsClass: {
            default: 'owl-dots'
        },
        dotClass: {
            default: 'owl-dot'
        },
        navContainerClass: {
            default: 'owl-nav'
        },
        navClass: {
            default: ['owl-prev','owl-next']
        },
        autoHeightClass: {
            default: 'owl-height'
        },
        responsiveClass: {
            default: false
        },
        loadingClass: {
            default: 'owl-loading'
        },
        loadedClass: {
            default: 'owl-loaded'
        },
      },
      
      mounted : function() {
        $('#' + this.elementHandle).owlCarousel({
            items        : this.items,
            margin       : this.margin,
            loop         : this.loop,
            center       : this.center,
            nav          : this.nav,
            autoplay     : this.autoplay,
            autoplaySpeed: this.autoplaySpeed,
            rewind       : this.rewind,
            mouseDrag    : this.mouseDrag,
            touchDrag    : this.touchDrag,
            pullDrag     : this.pullDrag,
            freeDrag     : this.freeDrag,
            stagePadding     : this.stagePadding,
            autoWidth     : this.autoWidth,
            autoHeight     : this.autoHeight,
            dots     : this.dots,
            dotsClass: this.dotsClass,
            dotClass: this.dotClass,
            navContainer: this.navContainer,
            navClass: this.navClass,
            autoplayTimeout     : this.autoplayTimeout,
            autoplayHoverPause     : this.autoplayHoverPause,
            responsive     : this.responsive,
            responsiveClass: this.responsiveClass,
            loadingClass: this.loadingClass,
            loadedClass: this.loadedClass
        });
      }
  }
</script>
