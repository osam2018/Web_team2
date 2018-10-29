<template>
    <el-container>
        <el-aside width="200px" class="aside">

            <side-menu></side-menu>
        </el-aside>
        <el-main class="Contact"><router-view/></el-main>
    </el-container>
</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import SideMenu from './side-page-sub/SideMenu.vue';
    import SidePage1 from './side-page-sub/SidePage1.vue';
    import SidePage2 from './side-page-sub/SidePage2.vue';

    @Component({
        components: {
            SideMenu,
            SidePage1,
            SidePage2,
        }
    })
    export default class SidePage extends Vue {
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

<style scoped>
</style>