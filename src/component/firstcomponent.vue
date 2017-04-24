<template>
    <div id="firstcomponent">
        <h1>I am a title.</h1>
        <a href="#"> written by {{author}}</a>
    </div>
</template>

<script type="text/ecmascript-6">
    export default{
        data () {
            return {
                author: '微信公众号： 凛冬将至'
            }
        }
    }
</script>