<template>
  <div id="home" class="home-nav">
    <nav-bar></nav-bar>
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar';
import {getHomeMultidata} from 'network/home';
export default {
    name:"Home",
    components:{
      NavBar
    },
    data(){
      return {
        banners : [],
        recommends :[]
      }
    },
    created(){
      getHomeMultidata().then(res=>{
        console.log(res);
        this.banners = res.data.banner.list;
        this.recommends = res.data.recommends.list;
      })
    }
}
</script>

<style scoped>
.home-nav{
  background-color: var(--color-tint);
  color :#fff;
}
</style>