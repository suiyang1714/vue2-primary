<template>
    <div id="secondcomponent">
        <h1>I am another page</h1>
        <a href="#"> written by {{author}}</a>
        <p>感谢 菜鸟大神指导=。</p>
        <ul>
            <li v-for="article in articles">
                {{ article.title }}
            </li>
        </ul>
    </div>
</template>

<script type="text/ecmascript-6">
    export default {
        data() {
            return{
                author: 'winter is coming ',
                articles: []
            }
        },
        mounted: function() {
            this.$http.jsonp('https://api.douban.com/v2/movie/top250?count=20', {}, {
                headers: {

                },
                emulateJSON: true
            }).then(function(response) {
                // 这里是处理正确的回调

                this.articles = response.data.subjects
                // this.articles = response.data["subjects"] 也可以

            }, function(response) {
                // 这里是处理错误的回调
                console.log(response)
            });
        }
    }
</script>