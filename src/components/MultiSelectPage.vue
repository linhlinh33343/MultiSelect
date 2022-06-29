<template >
   <div class="MultiSelectPage wrapper"  >
        <InputSelect :focused="focused" @clickInput="clickInput" />
        <ListSelect v-show="focused"
        @acceptList="acceptList"
        @addList="addList"
        :listProvinces="listProvinces"
        v-model="ListChecked"
        />
        <ResultMulti :ListChecked="ListChecked"  @deleteList="deleteList" v-show="showResult"/>
   </div>
</template>

<script>

import InputSelect from './InputSelect.vue'
import ListSelect from './ListSelect.vue'
import ResultMulti from './ResultMulti.vue'
export default {
    name:"MultiSelect",
    data(){
        return{
            focused:false,
            ListChecked:[],
            showResult:false,
        }
    },

    props:{
        listProvinces:{
            type:Array,
            default:()=>[]
        }
    },
    components:{
        InputSelect,
        ListSelect,
        ResultMulti
    },
    computed:{
       
    },
    watch: {
        focused() { 
            console.log('ok');
        },
        
    }
    ,
    methods:{
        
        addList(value){
            this.ListChecked=value;
        },
        clickInput(){
            this.focused=true;
           this.showResult=false;
        },
        deleteList(item){
            this.ListChecked = Array.from(this.ListChecked).filter((value) => value !== item);
           
        },
        acceptList(){
            this.showResult=true
            this.focused=false

        }
        
       
    }
   
    
}
</script>

<style>

</style>