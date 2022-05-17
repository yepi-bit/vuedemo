<template>
    <div>
        <wang-editor
                style='height:300px;'
                v-model='wangValue'
                :disabled='wangDisabled'
        ></wang-editor>
        <br />
        <br />
        <br />
        <br />
        <h5>双向绑定的源代码</h5>
        <div>{{wangValue}}</div>
        <h5>双向绑定的页面效果</h5>
        <div v-html='wangEditor'></div>
    </div>
</template>

<script>
    import wangEditor from '../components/wangeditor'
    export default {
        components:{wangEditor},
        data(){
            return {
                wangValue:'',
                wangDisabled:false
            }
        }
    }
</script>
