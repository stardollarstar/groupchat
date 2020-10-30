<template>
    <div id="chatrooms">
        <div id="profinfo">
            <div id="statcontainer">
                <div id="status">Group chat</div>
            </div>
        </div>
        <div id="chatholder">
            <Test :randomtext="text" />
        </div>
        <div id="chatinput">
            <input id="inputofchat" autocomplete="off" placeholder="Type a Message"  @keyup.enter="createchat()">
            <div id="sendbutton" @click="createchat()">Send</div>
        </div>
    </div>
</template>
<style scoped>
    #chatholder{
        overflow-y: scroll;
        width: calc(100% - 310px);
        height: calc(100% - 150px);
        position: absolute;
        margin-top: -20px;
        padding-top: 20px;
        margin-left: calc(100vw - 100%);
        margin-right: 0;
    }
</style>
<script>
import Test from './Test'

export default {
    el: "#chatrooms",
    components: {
        Test
    },
    data() {
        return {
            text: []
        }
    },
    methods: {
         createchat() {
            if(document.getElementById("inputofchat").value.length > 0) {
                this.text.push(document.getElementById("inputofchat").value);
                setTimeout(() => {
                    document.getElementById("chatholder").scrollTop = document.getElementById("chatholder").scrollHeight;
                }, 1);
                document.getElementById("inputofchat").value = '';
            }
        }
    }
}
</script>