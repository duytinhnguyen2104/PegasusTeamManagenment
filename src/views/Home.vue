<template>
      <div id="app">
        <Header />
        <img alt="Vue logo" src="../assets/Pegasus.jpg">
        <Members v-bind:members="members" v-on:del-member="deleteMember"/>
      </div>
</template>

<script>
    /* eslint-disable */
    import Members  from "@/components/Members.vue";
    import Header from "@/components/Layout/Header.vue";
    export default {
      name: "app",
      data() {
        return {
          members: [
            {
              id: 1,
              name: "Nguyen Duy Tinh",
              moved: true
            },
            {
              id: 2,
              name: "Mai Hoang Giang",
              moved: true
            },
            {
              id: 3,
              name: "Mai Tri Thuc",
              moved: false
            }
          ] 
        }
      },
      components: {
        Members,
        Header
      },
      methods:{
        deleteMember(id){
            this.members = this.members.filter(mem => mem.id != id)
        }
      }
    };
</script>
<style>
   *{
     box-sizing: border-box;
     margin: 0;
     padding: 0;
   }

   body {
     font-family:  Arial,Helvetica, sans-serif;
     line-height: 1.4;
   }
</style>