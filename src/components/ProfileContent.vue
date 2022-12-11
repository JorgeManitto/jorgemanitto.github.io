<template>
    <div class="carrousel">
    <swiper
      :modules="modules"
      :slides-per-view="1"
      :space-between="50"
      navigation
      :pagination="{ clickable: true }"
      :scrollbar="{ draggable: true }"
      @swiper="onSwiper"
      @slideChange="onSlideChange"
    > 
      <div style="position: absolute;top: 0;z-index: 99999999999999;left: 0;font-size: 1.2em;color: #fff;background: rgba(0,0,0,.5);padding: 5px;">Proyectos</div>
        <swiper-slide 
          v-for="item in items"
         :key="item"
         >
            
            <div class="h-200 h-500" style="width: 100%;background-repeat: no-repeat;background-size: cover;"
                :style="{ 'background-image': 'url(' + item.img + ')' }"
            >
                <div style="height: 100%;position: relative;">
                  <div style="position: absolute;margin: auto;height: auto;left: 40px;bottom: 10%;z-index: 9;">
                   
                    <div>
                      <div>
                        <img :src="item.icono" :alt="item.title" class="icono">
                      </div>
                      
                      <a :href="'http://'+item.volanta" class="text-white" target="_blank" style="z-index: 9999999999999999;">{{item.volanta}}</a>
                      
                      <h2 class="d-none d-lg-block text-white fw-bold lh-1" style="font-size: 2rem;z-index: 9999;">{{item.title}}</h2>
                      <h3 class="d-block d-lg-none text-white fw-bold ">{{item.title}}</h3>
                      
                      <p class="descripcion d-none d-lg-block">{{item.descripcion}}</p>
                      <div class="d-none d-lg-block">
                        <div v-if="(item.button_android && item.button_ios)" style="display: flex;z-index: 9999;margin-top: 1.5rem;">
                        <a href="{{item.button_android}}">
                          <img :src="item.imagen_android" alt="">
                        </a>
                        <a href="{{item.button_ios}}">
                          <img :src="item.imagen_ios" alt="">
                        </a>
                        </div>
                      </div>
                     
                    </div>

                  </div>
                </div>
                <div class="bg-destacada"></div>
            </div>
        </swiper-slide>
    </swiper>
    <about></about>
    </div>
  </template>
  <script>
    // import Swiper core and required modules
    import { Navigation, Pagination, Scrollbar, A11y } from 'swiper';
    
    // Import Swiper Vue.js components
    import { Swiper, SwiperSlide } from 'swiper/vue';
  
    // Import Swiper styles
    import 'swiper/css';
    import 'swiper/css/navigation';
    import 'swiper/css/pagination';
    import 'swiper/css/scrollbar';
    import { ref, onMounted } from 'vue';
    import About from './About.vue';
    // import {  } from '@vue/runtime-core';
  
    // Import Swiper styles
    export default {
      components: {
        Swiper,
        SwiperSlide,
        About
      },
      setup() {
        onMounted(() => {
          // console.log(elements.value);
        })
        const onSwiper = (swiper) => {
          // console.log(swiper);
          // return swiper;
        };
        const elements = ref([]);

        const items = [
            {
                id : 1,
                img : '/images/soyelcapitano.jpg',
                title : 'Full Stack Proyect Publisher, App, Comunity & Marketing Management',
                tecnologias : [1,3,4],
                icono : '/images/logo-elcapitano.jpg',
                volanta:'www.soyelcapitano.com/',
                descripcion:'The online sports news platform that only talks about soccer, the most beautiful sport in the world.',
                button_android : 'https://play.google.com/store/apps/details?id=biz.pupila.SoyElCapitano&pli=1',
                button_ios : 'https://apps.apple.com/sa/app/el-capitano/id1577846057',
                imagen_android : '/images/btn-google-play.png',
                imagen_ios : '/images/btn-app-store.png',
            },{
                id : 2,
                img : '/images/sanpedro.jpg',
                title : 'San Pedro Informa',
                tecnologias : [1,2],
                icono : '/images/sanpedro-icon.png',
                volanta:'www.sanpedroinforma.com.ar',
                descripcion:'San Pedro City News'
            },{
                id : 3,
                img : '/images/webinare.jpg',
                title : 'WebinARE',
                tecnologias : [1],
                icono : '/images/webinare-icon.png',
                volanta:'https://webinare.io/',
                descripcion:'Virtual events run on WebinARE help orchestrate your marketing and business development effort by conversations engaging your audience more intelligently while producing better opportunities.'
            },
            {
                id : 4,
                img : '/images/patagonia.jpg',
                title : 'Patagonia Press',
                tecnologias : [1,2,4],
                icono : '/images/patagonia-icon.png',
                volanta:'www.patagonia.press',
                descripcion:'Patagonia City News'
            },
            {
                id : 5,
                img : '/images/ain.jpg',
                title : 'Ain',
                tecnologias : [1,3,4],
                icono : '/images/ain-icon.png',
                volanta:'www.ain.com.ar',
                descripcion:'Islamic news agency, portal dedicated to events related to the Islamic world that happen daily in any region of the planet.'
            }
        ]
        const onSlideChange = (el) => {
          // console.log('slide change');
          // console.log(el);
          // return swiper;
        };
        const slideChange = (e) => {
          console.log(e);
        }
        console
        return {
          onSwiper,
          slideChange,
          onSlideChange,
          modules: [Navigation, Pagination, Scrollbar, A11y],
          items
        };
      },
    };
  </script>
<style scope>
.text-white{
  color:#fff;
}
.bg-destacada{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: url(https://www.annurtv.com/assets/bg-destacadas.png);
}
.icono{
  width: auto;
  height: 32px;
  object-fit: contain;
}
.descripcion{
  color:#fff;
  z-index: 9999;
}
.h-500{
  height: 500px;
}
.fw-bold{
  font-weight: 900;
}
.lh-1{
  line-height: 1;
}
@media (max-width:768px){
  .h-200{
    height:250px
  }
  }
</style>