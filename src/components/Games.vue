<template>
    <div class="games">
        <h2>游戏列表：</h2>
        <ul>
            <li v-for="g in games" v-bind:key="g.id">{{ g.name }}</li>
        </ul>
        <button @click="changeFirName">修改第一个游戏的名字</button>
        <div>{{ id }}; {{ name }}</div>
        <button @click="changeUpName">修改上面游戏的名字</button>
    </div>
</template>

<script lang='ts' setup name="Games">
    import { ref, reactive, toRefs, toRef } from 'vue'
    
    let games = ref([
        {id: 1, name:'英雄联盟1'},
        {id: 2, name:'英雄联盟2'},
        {id: 3, name:'英雄联盟3'}
    ])

    function changeFirName(){
        games.value[0] = {id: 4, name: '2333'}
        console.log(games)
    }


    let game_other = reactive(
        {id: 111, name:'三角洲1'}
    )
    let {id, name} = toRefs(game_other)
    let name_oth = toRef(game_other, 'name')
    

    function changeUpName(){
        console.log(toRefs(game_other))
        console.log(name_oth.value)
        id.value = 222
        name.value = '三角洲2'
    }

</script>

<style>
.games{
    background-color: skyblue;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
}
.li{
    font-size: 20px;
}
</style>