<template>
    <div class="ks-mainheader">
        <div class="ks-mainheader__content">
            <slick
                    ref="slick"
                    :options="slickOptions"
                    @afterChange="handleAfterChange"
                    @beforeChange="handleBeforeChange"
                    @breakpoint="handleBreakpoint"
                    @destroy="handleDestroy"
                    @edge="handleEdge"
                    @init="handleInit"
                    @reInit="handleReInit"
                    @setPosition="handleSetPosition"
                    @swipe="handleSwipe"
                    @lazyLoaded="handleLazyLoaded"
                    @lazyLoadError="handleLazeLoadError"
            >

                <div class="ks-mainheader-item" v-for="headeritem in blok">
                    <div v-if="headeritem[0].image_path !== undefined">
                        <pre>{{ headeritem }}</pre>
                    <picture>
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=400,width=1204' + headeritem[0].image_path + headeritem[0].image_desktop +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,dpr=2,fit=cover,height=400,width=1204' + headeritem[0].image_path + headeritem[0].image_desktop2x + ' 2x'" media="(min-width: 1200px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=400,width=1100' + headeritem[0].image_path + headeritem[0].image_desktop +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,dpr=2,fit=cover,height=400,width=1100' + headeritem[0].image_path + headeritem[0].image_desktop2x + ' 2x'" media="(min-width: 1000px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=400,width=1000' + headeritem[0].image_path + headeritem[0].image_desktop +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,dpr=2,fit=cover,height=400,width=1000' + headeritem[0].image_path + headeritem[0].image_desktop2x + ' 2x'" media="(min-width: 900px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=400,width=900' + headeritem[0].image_path + headeritem[0].image_tablet +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,dpr=2,fit=cover,height=400,width=900' + headeritem[0].image_path + headeritem[0].image_tablet2x + ' 2x'" media="(min-width: 800px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=400,width=800' + headeritem[0].image_path + headeritem[0].image_tablet +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,dpr=2,fit=cover,height=400,width=800' + headeritem[0].image_path + headeritem[0].image_tablet2x + ' 2x'" media="(min-width: 700px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=400,width=700' + headeritem[0].image_path + headeritem[0].image_tablet +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,dpr=2,fit=cover,height=400,width=700' + headeritem[0].image_path + headeritem[0].image_tablet2x + ' 2x'" media="(min-width: 600px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=400,width=600' + headeritem[0].image_path + headeritem[0].image_tablet +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,dpr=2,fit=cover,height=400,width=600' + headeritem[0].image_path + headeritem[0].image_tablet2x + ' 2x'" media="(min-width: 550px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=420,width=550' + headeritem[0].image_path + headeritem[0].image_mobile +'  1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,dpr=2,height=420,width=550' + headeritem[0].image_path + headeritem[0].image_mobile2x + ' 2x'" media="(max-width: 550px) and (min-width: 500px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=420,width=500' + headeritem[0].image_path + headeritem[0].image_mobile +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,dpr=2,height=420,width=500' + headeritem[0].image_path + headeritem[0].image_mobile2x + ' 2x'" media="(min-width: 400px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=420,width=400' + headeritem[0].image_path + headeritem[0].image_mobile +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,dpr=2,height=420,width=400' + headeritem[0].image_path + headeritem[0].image_mobile2x + ' 2x'" media="(min-width: 300px)">
                        <source  :srcset="'https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,height=420,width=300' + headeritem[0].image_path + headeritem[0].image_mobile +' 1x, https://assets.kapten-son.com/cdn-cgi/image/gravity=top,fit=cover,dpr=2,height=420,width=300' + headeritem[0].image_path + headeritem[0].image_mobile2x + ' 2x'" media="(min-width: 200px)">
                        <img :src="'https://assets.kapten-son.com/cdn-cgi/image/fit=cover,height=400,width=1204' + headeritem[0].image_path + headeritem[0].image_desktop2x " alt="Header"/>
                    </picture>
                    <div class="ks-mainheader-contentwrapper" :style="'margin-top:' + headeritem[0].margintop + ';margin-bottom:' + headeritem[0].marginbottom + ';margin-left:' + headeritem[0].marginleft + ';margin-right:' + headeritem[0].marginright ">
                        <h2  :style="{
                        '--button-fontheadlinecolor': headeritem[0].fontheadlinecolor}">{{ headeritem[0].headline}}</h2>
                        <p class="subline" :style="{
                        '--button-fontsublinecolor': headeritem[0].fontsublinecolor}">{{ headeritem[0].subline}}</p>
                        <a :href="headeritem[0].button_url" class="ks-mainheader-button" :style="{
                        '--button-background': headeritem[0].buttonbackground ,
                        '--button-color': headeritem[0].buttoncolor,
                        '--button-border': headeritem[0].buttonborder,
                        '--button-hover-background': headeritem[0].buttonhoverbackground,
                        '--button-hover-color': headeritem[0].buttonhovercolor,}">{{ headeritem[0].button}}</a>
                    </div>
                    </div>
                </div>
            </slick>
        </div>
    </div>
</template>
<script>
    import Slick from 'vue-slick'
    export default {
        components: { Slick },
        props: ['blok'],
        data() {
            return {
                locale: 'de',
                slickOptions: {
                    slidesToShow: 1,
                    slidesToScroll: 1,
                    autoplay: false,
                    arrows: true,
                    dots: false,
                    responsive: [
                        {
                            breakpoint: 1300,
                            settings: {
                                slidesToShow: 1,
                            }
                        },
                        {
                            breakpoint: 1024,
                            settings: {
                                slidesToShow: 1,
                            }
                        },
                        {
                            breakpoint: 768,
                            settings: {
                                slidesToShow: 1,
                                autplay: false,
                                speed: 1200,
                                autoplaySpeed: 5000
                            }
                        }
                    ]
                }
            }
        },
        methods: {
            next() {
                this.$refs.slick.next()
            },

            prev() {
                this.$refs.slick.prev()
            },

            reInit() {
                this.$nextTick(() => {
                    this.$refs.slick.reSlick()
                })
            },
            handleAfterChange(event, slick, currentSlide) {},
            handleBeforeChange(event, slick, currentSlide, nextSlide) {},
            handleBreakpoint(event, slick, breakpoint) {},
            handleDestroy(event, slick) {},
            handleEdge(event, slick, direction) {},
            handleInit(event, slick) {},
            handleReInit(event, slick) {},
            handleSetPosition(event, slick) {},
            handleSwipe(event, slick, direction) {},
            handleLazyLoaded(event, slick, image, imageSource) {},
            handleLazeLoadError(event, slick, image, imageSource) {}
        }
    }
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Oswald:300,400,500,700|PT+Serif:400,700');
$setting-font-family: 'PT Serif', serif;
$setting-font-family-additional: 'Oswald', sans-serif;

.ks-mainheader {
  border-radius: 0.25rem;
  overflow: hidden;
  position: relative;

  h2 {
    font-family: $setting-font-family-additional;
    text-transform: uppercase;
    font-size: 42px;
    color: var(--button-fontheadlinecolor);
  }

  p {
    font-family: $setting-font-family;
    color: var(--button-fontsublinecolor);
  }

  .subline {
    font-size: 28px;
  }

  &-item {
    position: relative;
    height: 100%;
    height: 400px;
  }

  &-contentwrapper {
    position: absolute;
    grid-template-columns: 1fr;
    justify-self: center;
    align-self: center;
    top: 50%;
    transform: translateY(-50%);
    width: 50%;
    left: 0;
    display: grid;
  }

  &.grid--center {
    align-self: center;
  }

  &.grid--middle {
    align-self: center;
  }

  .slick-initialized & {
    display: flex;
  }

  picture {
    position: absolute;
    top: 0;
    left: 0;
    height: 400px;
    width: 100%;

    img {
      max-height: none;
      max-width: none;

      &.right {
        float: right;
      }

      &.left {
        float: left;
      }
    }
  }

  a {
    text-decoration: none;
  }

  &-button {
    width: 220px;
    margin-top: 20px;
    padding-top: 10px;
    height: 50px;
    font-size: 1.1875rem;
    text-align: center;
    margin-left: 0;
    background: var(--button-background);
    color: var(--button-color);
    border: 1px solid var(--button-border);
    transition: all 0.5s ease;

    &:hover {
      background: var(--button-hover-background);
      color: var(--button-hover-color);
      border: 1px solid var(--button-border);
      transition: all 0.5s ease;
    }
  }

  .slick-slider {
    position: relative;
  }

  .slick-arrow {
    position: absolute;
  }

  .slick-next {
    top: 50%;
    transform: translateY(-50%);
    right: 20px;
  }

  .slick-prev {
    top: 50%;
    transform: translateY(-50%);
    left: 20px;
  }
}
</style>