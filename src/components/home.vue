<template>
  <div class="hello">
  	<div class="top"></div>
    <div id="content">
        <div class="d1">
          <one></one>
        </div>
        <div class="d2">
          <two></two>
        </div>
        <div class="d3">
          <three></three>
        </div>
    </div>
    <div id="content2">
        <div class="f1">
            <four></four>>
        </div>
        <div class="f2">
            <five></five>
        </div>
    </div>
  </div>
</template>

<script>
import one from './one.vue';
import two from './two.vue';
import three from './three.vue';
import four from './four.vue';
import five from './five.vue';
export default {
  name: 'hello',
  data () {
    return {

    }
  },
  components:{
    one,two,three,four,five
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .hello{
    background:#011128;
    min-width: 1280px;
    width: 100%;
  }
	.top{
		width: 100%;
		height: 85px;
    background:url("../assets/4.png") no-repeat;
    
	}

  #content{
    display: -webkit-flex;
    justify-content: space-around;
  }
.d1{
  width: 380px;
  height:500px;
}
.d2{
  width: 400px;
  height:500px;
}
.d3{
  width: 500px;
  height:500px;
}
 #content2{
     display: -webkit-flex;
     /* justify-content: space-around; */
     width: 100%;
 }
.f1,.f2{
  width:calc(100% / 2);
  margin: 10px;
}

</style>
