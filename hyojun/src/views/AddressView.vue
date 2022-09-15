<template>
  <div class="address">
    <h1>Address</h1>
    <input v-model="addr" />
    <button v-on:click="search">주소검색</button>
    <div>{{addrres}}</div>
  </div>
</template>

<script>
   import axios from 'axios'

    export default { 
        props: [],
        data: function() {
            return {
              addr : "",
              addrres : ""
            }
        },
        methods: {
          search() {
            axios.get("https://dapi.kakao.com/v2/local/search/address.json", {
                headers: {
                  Authorization: "KakaoAK [key]"
                },
                params: {
                  query: this.addr
                }
              }).then( (res) => {
                  // console.log(res.data);
                  this.addrres = res.data;
              }).catch((error) => {
                  console.log(error);
              });
            }
        },
        components: {
            
        },
        computed: {

        },
        watch: {

        },
        mounted: function() {
            console.log("mounted");
        },
        updated: function() {
            console.log("updated");
        },
    }
</script>