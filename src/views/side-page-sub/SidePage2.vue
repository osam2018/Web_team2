
<template>
    <el-main >
        <span style="color:darkseagreen;font-size:30pt"><I>Master Chat</I></span><br><br><br>
        <div><textarea id="chat_log" class="chat_log" readonly></textarea></div>
            <div id="_bottom">
                <textarea></textarea>
                <el-button class ="buttonb" type="primary">Write</el-button>
            </div>

    </el-main>

</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src

    @Component({

    })
    export default class Home extends Vue {}
</script>

<style scoped>
    .about{
        line-height: 30px;
    }
    * {
        -webkit-box-sizing: border-box;
        -moz-box-sizing: border-box;
        box-sizing: border-box;
    }

    body {
        margin: 0;
        padding: 0;
        background-color: darkseagreen;
    }
    .buttonb {
        display: inline-block;
        float: right;
        width: 100px;
        height: 100px;
        font-size: 17px;
        background-color: #eee;
        color: green;
        cursor: pointer;
        cursor: hand;
    }
    .chat_log {
        width: calc(100%);
        height: calc(500px);
        background-color:darkseagreen;
    }
    #_bottom {
        width: 100%;
        height: 100px;
        background-color: #fff;
    }

    #_bottom textarea {
        width: calc(100% - 100px);
        height: 100px;
        border: 1px solid darkseagreen;
        vertical-align: middle;
        padding: 5px;
        font-size: 15px;
    }
</style>