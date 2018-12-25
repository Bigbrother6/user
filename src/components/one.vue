<template>
  <div class="one">
    <div class="pic">
        <img src="../assets/5.jpg">
    </div>
    <ul>
        <li>姓名:张凯 </li>
        <li>学历:大专 </li>
        <li>年龄:25岁 </li>
         <li>籍贯:湖北黄冈 </li>
         <li>
         		博客:<a href="https://blog.csdn.net/big_borther6" target='_blank'>https://blog.csdn.net/big_borther6</a>
         </li>
         <li>
         	 gitHub:<a href="https://github.com/Bigbrother6" target='_blank'>https://github.com/Bigbrother6</a>
         </li>
         <li>联系电话:15811504412 </li>
         <li>电子邮箱:820839841@qq.com </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'one',
  data () {
    return {
          msg:"www"
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .one{
   width:100%;
   height:100%;
  border: 30px solid #4a444400;
    -o-border-image: url("../assets/1.png") 30 30 stretch;
    border-image: url("../assets/1.png") 30 30 stretch;
  }
  .pic{
    text-align:center;
  }
  .pic>img{
  	border-radius:50%;
    width: 150px;
    height: 150px;
  }
  .one>ul>li{
      color:#fff;
      padding:3px 0px;
  }
  a{
  	color: #409eff;
    text-decoration: none;
  }
</style>
