<template>
  <section class="main-slider bg-darkgray c-white">
    <no-ssr>
        <carousel :perPage='1'>
            <slide v-for='slide in slides'>
                <div class="container" :style="{ backgroundImage: 'url(' + slide.image + ')' }">
                    <div class="row middle-xs center-xs">
                        <div class="col-md-12 px10p">
                            <p class="subtitle mb0 serif uppercase h3 align-center">{{ slide.subtitle }}</p>
                            <h1 class="title mt0 mb30 align-center">{{ slide.title }}</h1>
                            <div class="align-center">
                                <button-outline class="button" :text="slide.button_text" color="light" />
                            </div>
                        </div>
                    </div>
                </div>
            </slide>
        </carousel>
    </no-ssr>
  </section>
</template>

<script>
import NoSSR from 'vue-no-ssr'
import { coreComponent } from 'lib/themes'
import { Carousel, Slide } from 'vue-carousel'
import ButtonOutline from '../../../theme/ButtonOutline.vue'

export default {
  components: {
    ButtonOutline,
    Carousel,
    Slide,
    'no-ssr': NoSSR
  },
  mixins: [coreComponent('core/blocks/MainSlider/MainSlider')]
}
</script>

<style scoped>
h1 {
    font-size: 72px;
}
.main-slider {
    width: 100%;
    height: 640px;
}
.container {
    width: 100%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
}
.row {
    height: 640px;
}
@media (max-width: 75em) {
    .main-slider {
        height: 400px;
    }
    .title {
        font-size: 50px;
    }
    .subtitle {
        font-size: 20px;
    }
    .row {
        height: 400px;
    }
}
@media (max-width: 64em) {
    .main-slider {
        height: 300px;
    }
    .title {
        font-size: 48px;
    }
    .subtitle {
        font-size: 18px;
    }
    .button {
        font-size: 16px;
    }
    .row {
        height: 300px;
    }
}
</style>