<template>
    <div class="date">
      <h1>{{date}}</h1>
    </div>
</template>

<script>
    export default { 
        // props: [] ,
        data: function() {
            return {
                date: '',
            }
        },
        //template: ``,
        methods: {
            
        },
        components: {
            
        },
        computed: {
            
        },
        watch: {
            
        },
        created: function() {
        var d = new Date();

        // 연도, 월, 일 추출
        var year = d.getFullYear();
        var month = d.getMonth() + 1;
        var day = d.getDate();

        // 최종 포맷 (ex - '2021-10-08')
        this.date = [year,((month < 10)? '0' + month: month),((day < 10)? '0' + day: day)].join('-');
        },
        mounted: function() {
            console.log("mounted");
        },
        updated: function() {
            console.log("updated");
        }
    }
</script>