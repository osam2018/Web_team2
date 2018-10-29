<template>
<el-main >
    <span class="sub_title"><I>Ticket</I></span><br><br><br>
        <h1>이름 : <el-input class="nameinput" placeholder="입력이 필요합니다.."></el-input></h1>
    <h1>제목 : <el-input class="nameinput" placeholder="입력이 필요합니다.."></el-input></h1>
        <h1>내용 : <el-input
                class="textr"
                type="textarea"
                :rows="4"
                placeholder="입력이 필요합니다.."
                >
        </el-input></h1>
    <el-upload
            class="upload-demo"
            action="https://jsonplaceholder.typicode.com/posts/"
            multiple
            :limit="3">
        <el-button size="default" type="primary">파일 업로드</el-button>
        <div slot="tip" class="el-upload__tip"></div>
    </el-upload>
        <el-button class ="Submitb"type="primary" @click="open">제출</el-button>
    </el-main>


</template>

<script>
    export default {
        methods: {
            open() {
                this.$message("당신의 Ticket은 성공적으로 제출되었습니다.");
            },
        }
    }//    export default class Home extends Vue {}
</script>

<style scoped>
    .nameinput{
        width: calc(100% - 100px);
    }
    .textr{
        width: calc(100% - 100px);
    }
    .Submitb{
        margin-right:calc(85%);
        width: calc(100px);
    }
    .upload-demo{
        margin-left:calc(85%);
    }
	.sub_title{
		font-size:40pt;
		color: #002761;
	}
</style>