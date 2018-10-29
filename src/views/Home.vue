<template>
    <el-container class="home">
		<!-- <Nav /> -->
        <el-main>
            <img class = "Home" alt="Alpha Mining logo" src="http://i.imgur.top/c/A/886714h3cdjbluelogo.png">
            <HelloWorld />
        </el-main>
    </el-container>
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

    @Component({
        components: {
            HelloWorld,
            Home
        }
    })
    export default class Home extends Vue {}
</script>

<style scoped>
    .Home{
		height:250px;
		width:600px;
		margin-top:20px;
    }
</style>