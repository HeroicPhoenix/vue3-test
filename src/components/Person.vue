<template>
    <div class="person2">
        <h2>当前求和为：{{ sum }}</h2>
        <button @click="sumPlus">点我+1</button>

        <h2>姓名：{{ person.name }}</h2>
        <h2>年龄：{{ person.age }}</h2>
        <button @click="changeName">姓名+~</button>
        <button @click="changeAge">年龄+1</button>
        <button @click="changePerson">全部改变</button>
        
    </div>
</template>

<script lang='ts' setup name="Person2">
    import { ref, reactive, computed, watch, toRefs, toRef } from 'vue'
    let sum = ref(0)
    function sumPlus(){
        sum.value += 1
    }
    const stopWatch = watch(
        sum,
        (newVal, oldVal) => {
            console.log(newVal, oldVal)
            if (newVal > 5) {
                stopWatch()
            }
        },
        
    )

    let person = ref({
        name: '张三',
        age: 18,
        sex: '男'
    })
    function changeName(){
        person.value.name += '~'
    }

    function changeAge(){
        person.value.age += 1
    }

    function changePerson(){
        person.value = {
            name: '李四',
            age: 80,
            sex: '女'
        }
    }

    watch(
        person,
        (newVal, oldVal) => {
            console.log(newVal, oldVal)
        },
        {
            deep: true
        }
    )
</script>
