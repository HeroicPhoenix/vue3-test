<template>
    <div class="person2">
        姓：<input type="text" v-model="firstName"></input>
        <br></br>
        名：<input type="text" v-model="lastName"></input>
        <br></br>
        姓名：<span>{{ fullName }}</span>
        <button @click="changeFullName">修改全名</button>
    </div>
</template>

<script lang='ts' setup name="Person2">
    import { ref, reactive, computed, toRefs, toRef } from 'vue'
    let firstName = ref('张')
    let lastName = ref('三')

    let fullName = computed({
        get(){
            console.log(1)
            return firstName.value.slice(0, 1) + '-' + lastName.value.slice(1, 2)
        },
        set(val){
            const [str1, str2] = val.split('-')
            firstName.value = str1
            lastName.value = str2
        }
        
    })
    
    function changeFullName(){
        fullName.value = 'li-si'
    }
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