<template>
    <el-main >
        <h4>side page 4</h4>
        <p>
            Consistent with real life: in line with the process and logic of real life, and comply with languages and habits that the users are used to.
            Consistent within interface: all elements should be consistent, such as: design style, icons and texts, position of elements, etc.
        </p>
        <h4>Feedback</h4>
        <p>
            Operation feedback: enable the users to clearly perceive their operations by style updates and interactive effects.
            Visual feedback: reflect current state by updating or rearranging elements of the page.
        </p>
        <h4>Efficiency</h4>
        <p>Simplify the process: keep operating process simple and intuitive.
            Definite and clear: enunciate your intentions clearly so that the users can quickly understand and make decisions.
            Easy to identify: the interface should be straightforward, which helps the users to identify and frees them from memorizing and recalling.
        </p>
        <h4>Controllability</h4>
        <p>Decision making: giving advices about operations is acceptable, but do not make decisions for the users.
            Controlled consequences: users should be granted the freedom to operate, including canceling, aborting or terminating current operation.
        </p>
    </el-main>

</template>

<script lang="ts">
    import { Component, Vue } from 'vue-property-decorator';
    import HelloWorld from '../../components/HelloWorld.vue'; // @ is an alias to /src

    @Component({

    })
    export default class Home extends Vue {}
</script>

<style scoped>
    .about{
        line-height: 30px;
    }
</style>