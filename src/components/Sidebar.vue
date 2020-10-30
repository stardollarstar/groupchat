<template>
    <div id="leftside">
        <div id="maincontainer">
            <div id="logo">
                VUE JS
            </div>
            <div id="profile"></div>
            <div id="name">
                <h3>Oreki</h3>Adminastrator
            </div>
            <div id="randomname">Menu</div>
            <div id="options">
                <div class="iconcontainer" @click="activeLink(0)">My Account</div>
                <div class="iconcontainer" @click="activeLink(1)">Logout</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            oldclass: -1
        }
    },
    methods: {
        activeLink(s) {
            if(this.oldclass != -1) {
                document.getElementsByClassName("iconcontainer")[this.oldclass].classList.remove("onchosen");   
            }
            document.getElementsByClassName("iconcontainer")[s].classList.add("onchosen");
            this.oldclass = s;
        }
    }
}
</script>