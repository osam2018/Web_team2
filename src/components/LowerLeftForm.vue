<template>
    <div class="form">
        <el-form ref="form" :model="form" label-width="120px" v-loading="loading">
            <el-form-item label="자산군">
                <el-tag
                        :key="tag"
                        v-for="tag in dynamicTags"
                        closable
                        :disable-transitions="false"
                        @close="handleClose(tag)">
                    {{tag}}
                </el-tag>


                <el-input
                        class="input-new-tag"
                        v-if="inputVisible"
                        v-model="inputValue"
                        ref="saveTagInput"
                        size="mini"
                        @keyup.enter.native="handleInputConfirm"
                        @blur="handleInputConfirm"
                >
                </el-input>
                <el-button v-else class="button-new-tag" size="small" @click="showInput">+ New Tag</el-button>

            </el-form-item>

            <el-form-item v-for="(asset, index) in assets" :label="asset.name">
                <div class="block">
                    <el-slider @change="handleChange(asset)" v-on:click="fix_slider(index)"
                               v-model="asset.weight"
                               show-input
                               :disabled="asset.slider_disable"
                    >
                    </el-slider>
                </div>
            </el-form-item>
        </el-form>
    </div>
</template>



<script lang="ts">
    import { Component, Prop, Vue } from 'vue-property-decorator';

    @Component({
        components: {
        },
        props:{
            form: Object,
            // assets: Array,
            // dynamicTags: Array
        }
    })
    export default class LowerLeftForm extends Vue {
        @Prop()
        private assets!:object[];
        @Prop()
        private dynamicTags!:object [];



        private component:any = '';
        private show_progress_bar:boolean = false;


        private inputVisible:boolean = false;
        private loading:boolean = false;
        private inputValue:string = '';


        updated(){
            this.$emit('value_change');
        }

        handleClose(tag:any) {
			if(this.assets.length == 1){
			}
			else{
				this.$emit('Close', tag);
			}
        }

        showInput() {
            this.inputVisible = true;
            this.$nextTick(function () {
                // this.$refs.saveTagInput.$refs.input.focus();
            })
        }

        handleInputConfirm() {
            let inputValue = this.inputValue;
            if (inputValue) {
                this.$emit('InputConfirm', inputValue)
            }
            this.inputVisible = false;
            this.inputValue = '';
        }

        handleChange(asset:any){
            this.$emit('SliderChange', asset);
        }

        // fix_slider(index){
        //     console.log("click");
        //     // this.assets[index].slider_disable = true
        // }


    }
</script>


<style scoped>


</style>
