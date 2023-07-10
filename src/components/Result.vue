<template>
  <p>Reaction time: {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
    props:['score'],
    data(){
        return {
            rank: null
        }
    },
    mounted(){
        if(this.score < 250){
            this.rank="Ninger Fingers"
        }
        else if(this.score < 400){
            this.rank="rapid fingers"
        }
        else{
            this.rank="small pace...."
        }
    }

}
</script>

<style>
.rank{
    font-size: 1.4em;
    color: #0faf07;
    font-weight: bold;
}

</style>