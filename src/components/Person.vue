<template>
    <div class="person">
        姓：<input type="text"></input>
        <br></br>
        名：<input type="text"></input>
        <br></br>
        姓名：<span>？？？</span>
    </div>
</template>

<script lang='ts' setup name="Person">
    import { ref, reactive, toRefs, toRef } from 'vue'
    
    

</script>

<style>
.person{
    background-color: skyblue;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}
.li{
    font-size: 20px;
}
</style>