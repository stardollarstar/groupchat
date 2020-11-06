<template>
    <div id="app">
        <ul id="kindamain">
            <li class="chats" v-for="item in randomtext" :key="item">
                <div id="name">{{name}}</div>{{item}}
            </li>
        </ul>
    </div>
</template>
<style scoped>
ul {
    margin-top: -20px;
    padding-top: 20px;
    list-style: none;
    padding-right: 40px;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    height: fit-content;
}
#name {
    position: absolute;
    margin-top: -26px;
    color: black;
    font-family: sans-serif;
    font-weight: bold;
    font-size: 14px;
    opacity: 1;
    margin-right: -10px;
}
#kindamain {
    width: 400px;
}
#app {
    display: flex;
    justify-content: flex-end;
}
.chats {
    border-radius: 10px 0px 10px 10px;
    font-weight: initial;
    width: fit-content;
    height: fit-content;
    margin-bottom: 25px;
    word-wrap: break-word;
    background-color: #412a50;
    color: white;
    padding: 10px;
    font-family: sans-serif;
    display: flex;
    justify-content: flex-end;
}
</style>
<script>
import data from "../data.json"

export default {

    el: "#app",
    data() {
        return{
            name: "Me"
        }
    },
    mounted: function() {
        console.log(data);
    },
    props: {
        randomtext: Array
    }
}
</script>