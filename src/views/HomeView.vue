<script>
import { onMounted } from '@vue/runtime-core'
// import { onMounted } from 'vue'
import ProfileContent from '../components/ProfileContent.vue'
import ProfileInfoVue from '../components/ProfileInfo.vue'
import ProfileItem from '../components/ProfileItem.vue'


export default {
  components: {
    ProfileContent,
    ProfileInfoVue,
    ProfileItem,
  },
  onMounted() {
    // console.log(this.$refs.child);
    // this.$refs.child will hold an instance of <Child />
    
  },
  data(){

    return { items : [
      {
        id : 1,
        title : 'VueJs',
        img : '/icons/vuejs-icon.png'
      },
      {
        id : 2,
        title : 'Angular',
        img : '/icons/angular-icon.webp'
      },
      {
        id : 3,
        title : 'Php',
        img : '/icons/php-icon.png'
      },
      {
        id : 4,
        title : 'Laravel',
        img : '/icons/laravel-icon.png'
      },
      {
        id : 5,
        title : 'JavaScript',
        img : '/icons/javascript-icon.webp'
      },
      {
        id : 6,
        title : 'Html',
        img : '/icons/html-icon.png'
      },
      {
        id : 7,
        title : 'Css',
        img : '/icons/css-icon.png'
      },
      {
        id : 8,
        title : 'Codeigniter',
        img : '/icons/codeigniter-icon.webp'
      },
      {
        id : 9,
        title : 'Ionic',
        img : '/icons/ionic-icon.webp'
      },
      {
        id : 10,
        title : 'Mysql',
        img : '/icons/mysql-icon.png'
      },
      {
        id : 10,
        title : 'Wordpress',
        img : '/icons/wp-icon.png'
      },
      {
        id : 11,
        title : 'AMP',
        img : '/icons/amp-icon.webp'
      },
      {
        id : 12,
        title : 'Liviwire',
        img : '/icons/livewire-icon.png'
      }
    ]
  }
  },


}

</script>

<template>
  <main class="container">
    <div class="row">
        <div class="col-lg-3 col-12">
          <ProfileInfoVue></ProfileInfoVue>
          <div style="margin-top:2rem;">Technologies:</div>
          <div class="card-item">
          
            <ProfileItem v-for="item in items" :key="item" class="profileitem">
              <template #img>
                <img width="32" height="32" :src="item.img" alt="">
              </template>
              <template #title>{{item.title}}</template>
            </ProfileItem>

          </div>
        </div>
        <ProfileContent ref="child" class="col-lg-9 col-12"></ProfileContent>
    </div>
    


  </main>
</template>
<style scoped>
.card-item {
 width: auto;
 height: auto;
 color: white;
 display: grid;
 grid-template-columns: 1fr 1fr 1fr 1fr;
 grid-template-rows: 1fr;
 gap: 5px;
 overflow: visible;
 background-color: transparent;
}
.profileitem{
  height:100px;
}
</style>