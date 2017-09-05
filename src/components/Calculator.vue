<template>
    <div class="calculator">
        <div class="input-box">{{text}}</div>
        <div class="key-box">
            <span v-for="(item,index) in numList" :key="item.value" :class="item.icon" @click="doAction(item.value)">{{item.text}}</span>
        </div>
    </div>
</template>

<<script>
export default {
    name:"calculator",
    data:function(){
        return{
            flag:false,
            text:"",
            textList:[],
            numList:[
                {text:"+",value:"+",icon:"icon icon01"},
                {text:"-",value:"-",icon:"icon icon02"},
                {text:"*",value:"*",icon:"icon icon03"},
                {text:"/",value:"/",icon:"icon icon04"},
                {text:"<",value:"<",icon:"icon icon06"},
                {text:"1",value:1},
                {text:"2",value:2},
                {text:"=",value:"=",icon:"icon icon05"},
                {text:"3",value:3},
                {text:"4",value:4},
                {text:"5",value:5},
                {text:"6",value:6},
                {text:"7",value:7},
                {text:"8",value:8},
                {text:"9",value:9},
                {text:"0",value:0}
            ]
        }
    },
    watch:{
        "textList":function(val,oldval){
            this.text = "";
            this.text = this.textList.join("");
        }
    },
    methods:{
        doAction:function(value){
            if (value=="=") {
                if(this.textList.length>0){
                    var last = this.textList[this.textList.length-1]
                    if (last=="+"||last=="-"||last=="*"||last=="/") {
                        return false;
                    }
                    this.flag = true;
                    this.textList = [eval(this.text)]
                }
            }else if(value=="<"){
                if(this.textList.length>0){
                    this.textList.pop();
                    this.flag = false;
                }
            }else{
                if (this.textList.length==0) {
                    if(value=="+"||value=="-"||value=="*"||value=="/"){
                        return false;
                    }
                }
                if (this.textList.length>0&&this.flag) {
                    if(value=="+"||value=="-"||value=="*"||value=="/"){
                        var last = this.textList[this.textList.length-1]
                        if ((last=="+"||last=="-"||last=="*"||last=="/")&&(value=="+"||value=="-"||value=="*"||value=="/")) {
                            return false;
                        }
                        this.textList.push(value);
                        this.flag = false;
                    }
                    if(value>=0&&value<=9){
                        this.textList = [value];
                        this.flag = false;
                    }
                }else{
                    var last = this.textList[this.textList.length-1]
                    if ((last=="+"||last=="-"||last=="*"||last=="/")&&(value=="+"||value=="-"||value=="*"||value=="/")) {
                        return false;
                    }
                    this.textList.push(value);
                }
            }
        }
    }
}
</script>


<style lang="less">
.calculator {
    height: 100%;
    width: 100%;
    .input-box {
        height: 120px;
        background: #fff;
        text-align: left;
        font-size: 26px;
        line-height: 40px;
        padding: 10px;
    }
    .key-box {
        height: auto;
        overflow: hidden;
        padding: 15px 0;
        span {
            display: inline-block;
            width: 70px;
            height: 60px;
            line-height: 60px;
            font-size: 28px;
            border: 1px solid #d5d5d5;
            margin: 2px;
            border-radius: 5px;
        }
        .icon {
            text-indent: -9999px;
        }
        .icon01 {
            background: url(../assets/icon_01.png) no-repeat center center;
            background-size: 50%;
        }
        .icon02 {
            background: url(../assets/icon_02.png) no-repeat center center;
            background-size: 50%;
        }
        .icon03 {
            background: url(../assets/icon_03.png) no-repeat center center;
            background-size: 50%;
        }
        .icon04 {
            background: url(../assets/icon_04.png) no-repeat center center;
            background-size: 50%;
        }
        .icon05 {
            background: url(../assets/icon_05.png) no-repeat center center;
            background-size: 40%;
        }
        .icon06 {
            background: url(../assets/icon_06.png) no-repeat center center;
            background-size: 40%;
        }
    }
}
</style>

