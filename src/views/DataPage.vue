<template>
    <el-main class="Mining">
        <br><br>
        <span class="sub_title">Alpha Mining Tool</span><br><br><br>
        <p class="text1">
            저희 회사가 자랑하는 "Alpha Mining Tool"을 이용해 여러분의 미래를 설계 해보십시오.
        </p><br><br><br>
	<AssetAllocationPage />
    </el-main>

</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
	import Result from '../components/Result.vue';
	import AssetAllocationPage from '../components/AssetAllocationPage.vue'

    @Component({
        components:{
            DataPage,
		  	Result,
      		AssetAllocationPage
        }
    })
    export default class DataPage extends Vue {}
</script>

<style scoped>
    .about{
        line-height: 30px;
    }
	.sub_title{
		font-size:40pt;
		color: #002761;
	}
	.text1{
		font-size:13pt;
		color: #002761;
		font-style: italic;
	}
	.text_color{
		color: #002761;
	}
</style>