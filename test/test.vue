<style lang="less" scoped>
    .cron{
        width: 400px;
        margin: 0 auto;
        margin-top: 100px;
        h1{
            font-size: 50px;
            text-align: center;
        }
    }
</style>

<template>
    <div class="cron">
        <h1>vue-cron</h1>
        <el-popover v-model="cronPopover">
            <vueCron v-model="cronValue" :data="cron" @change="changeCron" @close="cronPopover=false" i18n="en"></vueCron>
            <el-input slot="reference" @click="cronPopover=true" v-model="cron" placeholder="* * * * * ? *"></el-input>
        </el-popover>

    </div>
</template>

<script>

    export default {
        data(){
            return {
                cronPopover:false,
                cron:'',
                cronValue: '* * * * * ? *'
            }
        },
        components: {  },
        computed: {},
        methods: {
            changeCron(val){
                this.cron=val
            },
        },
        mounted(){

        }
    }
</script>
