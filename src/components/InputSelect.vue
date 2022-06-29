<template>
    <div class="InputSelect"  >
        <div :class="['select-control']" @click="handleClick()" >
            <input  class="select-input" type="text" placeholder="Chọn tỉnh thành" >
            <i class="select_icon fa-solid fa-caret-down"></i>
        </div>
    </div>
</template>
<script>
export default {
    
    name:'InputSelect',
    data(){
        return {
          
        }
    },
    components:{
       
    },
    props:{
      focused:{
        type:Boolean,
      }
        
    },
   
    methods:{
        handleClick(){
            
            this.$emit('clickInput')
          
        },
    }

}
</script>

<style>
    :root {
        --heightMultiOptions:304px;
        --heightButton:64px;
    }
    .label{
        width: 100%;
        display: block;
    }
    .multiselect{
        position: relative;
    }
    .select-control{
        display: flex;
        border-radius: 5px;
        box-shadow: 0px 0px 3px 0px #007bc3;
        border: 1px solid transparent;
        align-items: center;
    }
    .select-input{
        flex: 1;
        outline: none;
        border: none;
        font-size: 16px;
        padding: 15px 10px 15px 10px;
        border-radius: 10px;

    }
    
    .select_icon {
        padding:5px 10px;
        font-size: 20px;
        cursor: pointer;
    }
    .select_icon:hover{
        opacity: 0.5;
    }
    .isClick{
        border: 1px solid rgba(160, 160, 228, 0.952);
    }
    .multiselect-list{
        margin-top: 4px;
        border-radius: 4px;
        box-shadow: 0 0 10px 0.5px rgb(0 0 0 / 15%);
        
    }
    .multiselect-options{
        height:calc(var(--heightMultiOptions) - var(--heightButton));
   
         padding-left: 0;
        margin: 0;
     
        overflow-y:scroll;
        border-radius: 4px;

    }
    .multiselect-option{
       
        display: flex;
        justify-content: start;
        align-items: center;
        padding: 9px 0;
        cursor: pointer;
    
    }
    .multiselect-option:hover{
        background-color: #e7f1fd;
        
    }
    input[type="checkbox"]{
        width: 16px;
        height: 16px;
        margin-right: 8px;
    }
    ::-webkit-scrollbar {
        width: 8px;
        height: 62px;
        border-radius: 6px;
    }
    ::-webkit-scrollbar-thumb {
        background: #dcdcdc;
        width: 8px;
        height: 62px;
        border-radius: 6px;
    }
  


</style>