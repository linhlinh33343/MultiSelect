<template>
     <div class="province-result">
    <div class="list-province" >
        <div class="item-province" v-for="(item, index) in ListChecked" :key="index">
            <span class="province-name">{{item}}</span>
            <i @click="cancelItem(item)" class="close-button fa-solid fa-xmark"></i>
        </div>
    </div>
  </div>
</template>
<script>
export default {
    name: "ResultMulti",
    props:{ 
        ListChecked:{
            type:Array,
            default:()=>[]
        }
    },
    methods:{
       
        cancelItem(item){
            
            this.$emit('deleteList',item)

        }
    }
}
</script>

<style>
.province-result {
    /* position: absolute;
    top: 100%; */
    width: 100%;
    height: var(--heightMultiOptions);
    margin-top:5px;
    border-radius: 4px;
    box-shadow: 0 0 10px 0.5px rgb(0 0 0 / 15%);
}

.item-province {
    display: inline-block;
    float: left;
    padding: 10px;
    background-color: #f8f8f8;
    margin: 5px;
    border-radius: 25px;
   
}
span.province-name {
    font-size: 16px;
  
}
.close-button{
    padding: 3px;
    margin-left: 8px;
}
    
</style>