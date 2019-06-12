<template>
    <!-- <div class="home">
        <h1>主页内容</h1>
    </div> -->
    <div class="home">
        <button @click="showCont">显示表格</button>
        <div v-if="show">
        <table >
            <tr class="field">
                <td>id</td>
                <td>IMEI</td>
                <td>device</td>
                <td>message</td>
                <td>tel</td>
                <td>createdAt</td>
            </tr>
            <tr v-for="index in syk" class="content">
                <td>{{index.id}}</td>
                <td>{{index.IMEI}}</td>
                <td>{{index.device}}</td>
                <td>{{index.message}}</td>
                <td>{{index.tel}}</td>
                <td>{{index.createdAt}}</td>
            </tr>
            <!-- <p>syk:{{ syk }}</p> --> 
        </table>
        </div>
           
    </div>
</template>
<script>
export default {
    name:"index",
    data(){
        return{
           syk:'', 
           show:true
        }
    },
    created(){
        this.axios.get('http://localhost:60020/all').then((response) => {
        console.log(response.data.data[1]);
        this.syk=response.data.data;
            console.log(this.syk);
        }).catch((error)=>{
             console.log(error)
        })
    },
    methods:{
    showCont:function(){
    this.show = !this.show;
        }
    }
}
</script>

<style>
/* .home{
    width:1920px;
    height: 100%;
    background: url('../assets/bg.jpg') no-repeat;
} */
table{
    margin: 0 auto;
}
table h3{
    color: rgb(216, 26, 1);
}
table tr td{
    width:70px;
    height: 30px;
}
.field{
    text-align: center;
    background:rgb(61, 222, 228);
}
.content{
    text-align: center;
    background:rgb(241, 132, 174); 
}
button{
    margin: 0 auto;
    background: gold;
}
</style>
