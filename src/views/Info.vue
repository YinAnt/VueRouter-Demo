<template>
    <div v-bind:id='bg1'>
        <div class="info">
        <h1>This is an info page</h1>
        </div>
        {{msg}} <br>
        {{msg1}} <br>
        {{count}} <br>
        <div v-html='template'></div>
        <a v-bind:href="url">百度</a> <br>
        <button type="button" v-on:click="submit">submit</button> <br>
        <div name='v-if-test'>
            <div v-if='count<0'>count < 0</div>
            <div v-else-if='count==0'>count = 0</div>
            <div v-else-if='count>0 && count<2'>0 < count < 2</div>
            <div v-else>count >= 2</div>
            <div v-show='count == 0'>v-show count == 0</div>
        </div>
        <div name="list-test">
            <div v-for="item in list" :key="item">{{item.name}}</div>
        </div>
    </div>
</template>

<script>
    var app = new Vue({
        el:'#app',
        data:{
            bg1:'app-bind',
            msg:'hello message',
            count:-1,
            template:'<div>hello template</div>',
            url:'http://www.baidu.com',
            list:[{
                name:'zs',age:'10'
            },{
                name:'ls',age:'20'
            }]
        },
        methods:{
            submit:function(){
                this.count ++;
            }
        },
        watch:{
            msg:function(newVal,oldVal){
                console.log('new Val is ' + newVal)
                console.log('old Val is ' + oldVal)
            }
        },
        computed:{
            msg1:function(){
                return 'computed:'+this.msg+',count:'+this.count
            }
        }
    })
</script>