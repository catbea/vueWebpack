<template>
  <div class="view-container">
      <div class="content" v-if="indexData">
            <ul>
                <li v-for="(item,index) in  indexData" :key="index">
                    <p class="abstract" v-html="item.abstract"></p>
                    <img :src="item.large_image_url" alt="">
                </li>
            </ul>
      </div>
  </div>
</template>
<script>
var appData = require("../../data.json");
export default {
    name:'elmIndex',
    data(){
        return {
            indexData:[]
        }
    },
    created(){
        this.initIndexData();
        this.indexData =appData.data;

        console.log(this.indexData);
    },
    methods:{
        initIndexData:function(){      

            // this.$http.get('https://m.toutiao.com/list/?tag=__all__&ac=wap&count=20&format=json_raw&as=A1158A0CB81F2CF&cp=5AC85FB24C0FEE1&max_behot_time=1523118788&_signature=HhJLjAAARN6wWQYtrTSOuR4SS5&i=1523118788')
            // .then(response => {            
            //     // get body data
            //     this.indexData = response.body;

            //      console.log(this.indexData);   
            
            // }, response => {
            //     // error callback
            //     console.log(response.body);
            //     console.log("网络错误");

            // });
        }
    }
}
</script>
<style>
    img{
        max-width: 100%;
    }
    .view-container .content{
        width: 100%;
        padding: 2%;
    }
    .content ul li .abstract{
        text-align: initial        
    }
</style>

