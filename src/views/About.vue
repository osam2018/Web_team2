<template>
    <el-main class="About">
        <br><br>
        <span class="sub_title"><I>Alpha란?</I></span>
        <p class="text1">
           Alpha란 시장대비 초과수익률을 말하며, Alpha가 높을수록 귀하의 수익률이 시장상황에 비해 더 좋다고 말 할 수 있습니다.
        </p><br><br>
        <span class="sub_title"><I>Alpha Mining!</I></span>
        <p class="text1">
            저희 사이트에 방문하신것을 진심으로 환영합니다!
            저희 사이트의 데이터 분석 시스템은 귀하의 투자전략에 많은 보탬이 될 것입니다.<br><br><br><br>
        </p>
        <span class="sub_title"><I>Alpha Mining과 함께하십시오!</I></span><br>
        <p class="text1">
            저희 투자 전문가들은 언제나 고객을 기다리고 있습니다.
            <br>
        </p>
        <img src="https://image.freepik.com/free-vector/happy-emoji_53876-25513.jpg" align="left" class="face1">
        <div style="text-align: left;"><br>
        <span style="margin-left:100px;font-size:15pt"><I>이름 : Alex</I></span><br><br>
         <span style="margin-left:100px;font-size:15pt"><I>나이 : xx세</I></span> <br><br>
            <span style="margin-left:100px;font-size:15pt"><I>휴대폰 : 010-xxxx-xxxx</I></span> <br><br><br><br>
            <span style="color:black;font-size:14pt"><I>약력</I></span>
            <el-table
                    class="person1"
                    :data="tableData"
                    stripe
                    style="width: 100%">
                <el-table-column
                        prop="date"
                        label="기간"
                        width="180">
                </el-table-column>
                <el-table-column
                        prop="name"
                        label="내용"
                        width = calc(100%)>
                </el-table-column>
            </el-table>
            <br><br><br><br>
        </div>
        <img src="https://image.freepik.com/free-vector/happy-emoji_53876-25513.jpg" align="left" class="face1">
        <div style="text-align: left;">
            <br>
            <span style="margin-left:100px;font-size:15pt"><I>이름 : Brown</I></span><br><br>
            <span style="margin-left:100px;font-size:15pt"><I>나이 : xx세</I></span> <br><br>
            <span style="margin-left:100px;font-size:15pt"><I>휴대폰 : 010-xxxx-xxxx</I></span> <br><br><br><br>
            <span style="color:black;font-size:14pt"><I>약력</I></span>
            <el-table class="person1"
                      :data="tableData1"
                      stripe
                      style="width: 100%">
                <el-table-column
                        prop="date"
                        label="기간"
                        width="180">
                </el-table-column>
                <el-table-column
                        prop="name"
                        label="내용"
                        width = calc(100%)>
                </el-table-column>
            </el-table>
        </div><br><br><br>
        <span class="sub_title"><I>언제든지 연락주십시오!</I></span><br><br><br>

    </el-main>

</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

    @Component({
        components:{
            About
        }
    })
    export class About extends Vue {}
    export default {
        data() {
            return {
                tableData: [{
                    date: '1970~1973',
                    name: 'XX대학교 금융학과 졸업',
                }, {
                    date: '1974~1980',
                    name: 'XX컴퍼니 투자설계부',
                }, {
                    date: '1980~ 현재',
                    name: 'Alpha Mining 투자 설계 및 분석 담당 고문',
                }, ],
                tableData1: [{
                    date: '1970~1973',
                    name: 'ZZ대학교 금융학과 졸업',
                }, {
                    date: '1974~1980',
                    name: 'ZZ컴퍼니 초대 설립 및 투자 분석 고문',
                }, {
                    date: '1980~ 현재',
                    name: 'Alpha Mining 투자 기획 및 관리 과장',
                }, ]
            }
        }
    }
</script>

<style scoped>
    .About{
        /* background-image: url("//i.imgur.top/c/A/373022oa5kcstock.jpg"); */
        background-size: cover;
    }
    .face1{
        width:200px;
        height:200px;
    }
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
</style>