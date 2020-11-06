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
            <input id="inputofchat" v-model="currentchat" autocomplete="off" placeholder="Type a Message"  @keyup.enter="createchat()">
            <div id="sendbutton" @click="createchat()">Send</div>
        </div>
    </div>
</template>
<style scoped>
    #chatholder{
        overflow-y: scroll;
        width: 80%;
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
import data from '../data.json'

export default {
    el: "#chatrooms",
    components: {
        Test
    },
    data() {
        return {
            currentchat: '',
            text: []
        }
    },
    mounted: function() {
        for(var i = 0; i < data.chats.length; i++) {
            this.text.push(data.chats[i].chat);
        }
    },
    methods: {
         createchat() {
            if(this.currentchat.length > 0) {
                this.text.push(this.currentchat);
                data.chats.push({chat: this.currentchat});
                setTimeout(() => {
                    document.getElementById("chatholder").scrollTop = document.getElementById("chatholder").scrollHeight;
                }, 1);
                this.currentchat = '';
            }
        }
    }
}
</script>