<template>
    <el-menu
            default-active="sidepage1"
            class="el-menu-vertical-demo"
            @open="handleOpen"
            @select="handleSelect"
            @close="handleClose">
        <el-menu-item index="sidepage1">
            <i class="el-icon-tickets"></i>
            <span>Ticket</span>
        </el-menu-item>
		
		
		
        <el-button class="question" type="default">영업시간 외 문의는<br><br> Ticket을 활용해주시기 <br><br>바랍니다.<br><br>영업시간 <br><br>AM 09:00 ~<br><br>PM 06:00</el-button>
    </el-menu>
</template>

<script lang="ts">
    import {Component, Prop, Vue} from 'vue-property-decorator';

    @Component
    export default class SideMenu extends Vue {
        public activePage:string ="SidePage1";

        handleOpen(key:string, keyPath:string) {
            console.log("open ", key, keyPath);
        }

        handleClose(key:string, keyPath:string) {
            console.log("close", key, keyPath);
        }

        handleSelect(key:string, keyPath:string){
            console.log("select", key, keyPath);
            this.$router.replace("/sidepage/"+key);
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
    .question{
        width:200px;
        font-size:15px;
		margin-top:350px;
		color:#002761;
		border-color:white;
		background-color:white;
    }
	el-menu{
		background-color:white;
	}
</style>
