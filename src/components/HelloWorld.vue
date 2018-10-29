<template>
  <div class="hello">
      <router-link to="About">
  <el-button class="button1">
		  <span class="contents_title"><I>Alpha Mining</I></span><br><br><br>
    <span class="desc_text">Alpha란 무엇인가?<br><br></span>
      <span class="desc_text">AlphaMining Service를 당장 활용해보세요!<br><br><br></span>
      </el-button>
	</router-link>
	  
      <router-link to="DataPage">
          <el-button class="button2">
			  <span class="contents_title"><I>Minning Tool</I></span><br><br><br>
			  <span class="desc_text">Alpha Mining 서비스<br><br></span>
			  <span class="desc_text">차트를 활용한 사용자 인터페이스<br><br><br></span>
    	</el-button>
	</router-link>
	  
  <router-link to="SidePage">
  	<el-button class="button3"><span class="contents_title"><I>Contact</I></span><br><br><br>
      <span class="desc_text">어려움이 있으시다면<br><br></span>
      <span class="desc_text">저희 Alpha Mining의 최고의 투자자들과<br><br></span>
      <span class="desc_text">Ticket을 통해 소통하십시오.</span></el-button></router-link>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  @Prop() private msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .button2{
    width:400px;
    height:300px;
    margin-right:50px;
    /*background-image: url("//i.imgur.top/c/A/308998ber3prealcatter.jpg");*/
    background-size: cover;
  }
  .button1{
    width:400px;
    height:300px;
    margin-right:50px;
    /*background-image: url("//i.imgur.top/c/A/373022oa5kcstock.jpg");*/
    background-size: cover;
  }
  .button3{
    width:400px;
    height:300px;
      margin-right:50px;
      /*background-image: url("//i.imgur.top/c/A/359144487ifready.jpg");*/
      background-size: cover;
  }
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
	
.desc_text{
	color:#002761;
	font-size:14pt;
}
.contents_title{
	color:#002761;
	font-size:35pt;
}
.hello{
	margin-top:100px;
	margin-bottom:80px;
}
</style>
