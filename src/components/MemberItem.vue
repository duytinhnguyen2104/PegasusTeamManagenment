<template>
    <div class="member-Item" v-bind:class = "{'is-Moved':member.moved}">
        <p>
            <input type="checkbox" v-on:change = "selectMember">   
            {{member.name}} 
            <button @click="$emit('del-member',member.id)" class="del">x</button>
        </p>
    </div>
</template>
<script>
export default {
    name: "MemberItem",
    props: [
        "member"
    ],
    methods:{
        selectMember() {
            this.member.moved = !this.member.moved
        }
    }
}
</script>
<style scoped>
    .member-Item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted
    } 

    .is-Moved{
        text-decoration: line-through
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
    }
</style>