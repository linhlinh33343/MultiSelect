<template>
    <div class="province-control ">
        <button class="province-btn" :class="[provincelist.length>0?'active':'']" @click="acceptList">Đồng Ý</button>
        <a class="province-link" @click="cancelList">Hủy</a>
    </div>
</template>

<script>

export default {
    
    name:"ButtonVue",
    data(){
        return {
            
            
        }
    },
    computed:{
        
    },
     props:{
        provincelist:{
            type:Array,
            default:()=>[]
        }
    },
    
    methods:{
        acceptList(){
            this.$emit("acceptList")
            
        },
        cancelList(){
            this.$emit("cancelList");
        }

    },
    
}
</script>

<style>
.province-control{
    padding-left: 16px;
   display: flex;
   justify-content:start;
   align-items:center;
   padding: 16px 0 16px 16px;
}
.province-btn{
    width:104px;
    height:32px;
    font-size: 16px;
    background-color:#dcdcdc;
    border-radius: 4px;
    border: none;
    outline: none;
    color: white;
    box-shadow: 0 0 0px 1px #dcdcdc;
    margin-right: 12px;
    

}
.province-btn.active{
    background-color:#007bc3;
    color: white;
}
.province-btn.active:hover{
    background-color:#0371b1;
}
.province-link{
    width: 82px;
    height:24px;
     font-size: 16px;
     color: #007bc3;
     display: flex;
     justify-content: center;
     align-items: center;
     cursor: pointer;
}

</style>