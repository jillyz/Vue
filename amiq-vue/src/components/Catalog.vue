<template>
  <div class="gridBook">
    <div v-for="(stageData,index) in this.bookData" :key="index">
        <a :class="`stage-bg stage-bg-${stageData.stage}`">
            <h2>AMIQ 第 {{stageData.stage}}階（{{stageData.stageName}}）</h2>
            <p>{{stageData.content}}</p>
        </a>
        <div v-for="(book,number) in stageData.books" :key="number"
             :id="`guid_${book.guid}`" 
             data-ga="BookGrid" 
             :data-value="`${book.id}`" 
             :class="`books stage-${stageData.stage} book-guid-${book.guid}`">
            <div :class="`item item-grid stage stage-${stageData.stage}`">
                <div class="info">
                    <span class="title">
                        <span class="id">{{book.id}}</span>
                        <span class="ch">{{book.title}}</span>
                    </span>
                    <span class="subject">{{book.subject}}</span>
                </div>
                <div class="topics">
                    <!-- <img src="../assets/content_s/amiq101.jpg" alt=""> -->
                    <img src="https://jillyz.github.io/amiq/img/content_s/amiq101.jpg" alt="">
                </div>
            </div>
        </div>
    </div>
  </div>
</template>

<script>
// import GameCard from '../components/CatalogGridItem.vue';

export default {
    name: 'Game',
    components: {
        // CatalogGridItem,
    },
    props: {

    },
    data(){
        return{
            bookData:[]
        }
    },
    mounted(){
        this.getBookData();
    },
    methods:{
        getBookData:function(){
            // fetch('https://www.ezding.com.tw/new_ezding/ranking_list/order_top?page=1&page_size=10')
            fetch('https://jillyz.github.io/amiq/data/data.json')
            .then(response => response.json())
            .then(data => {
                this.bookData = data;
                console.log(this.bookData)
            })
            .catch(error=>{
            });
            
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .stage:before {
        content: "";
        position: absolute;
        top: 0;
        left: 0;
        z-index: 10;
        height: 10px;
        width: 60px;
        border-top: 10px solid #fc0;
    }

    .stage:after {
        content: "";
        position: absolute;
        top: 0;
        left: 60px;
        z-index: 10;
        height: 10px;
        width: calc(100% - 60px);
        border-top: 10px solid;
    }

    .stage-1:after {
        border-top-color: #3aa241;
    }

    .stage-2:after {
        border-top-color: #1cbcb4;
    }

    .stage-3:after {
        border-top-color: #ef452e;
    }

    .stage-4:after {
        border-top-color: #fb8809;
    }

    .stage-5:after {
        border-top-color: #056abc;
    }

    .stage-6:after {
        border-top-color: #00b0d9;
    }

    .stage-bg {
        display: block;
        /*margin-top: 1em;*/
        margin-bottom: 1px;
        padding: 1em 2em;
        /*background-color: #efefef;*/
        color: #fff;
        /*border-left: 10px solid;*/
    }

    .stage-bg h2 {
        margin-top: 1em;
    }

    .stage-bg-1 {
        background-color: #3aa241;
    }

    .stage-bg-2 {
        background-color: #1cbcb4;
    }

    .stage-bg-3 {
        background-color: #ef452e;
    }

    .stage-bg-4 {
        background-color: #fb8809;
    }

    .stage-bg-5 {
        background-color: #056abc;
    }

    .stage-bg-6 {
        background-color: #00b0d9;
    }
</style>
