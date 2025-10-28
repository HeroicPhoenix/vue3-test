<template>
    <div class="person2">
        <h2>当前求和为：{{ sum }}</h2>
        <button @click="sumPlus">点我+1</button>
    </div>
</template>

<script lang='ts' setup name="Person2">
    import { ref, reactive, computed, watch, toRefs, toRef } from 'vue'
    let sum = ref(0)
    function sumPlus(){
        sum.value += 1
    }
    watch(
        sum,
        (newVal, oldVal) => {
            console.log(newVal, oldVal)
        }
    )
</script>
