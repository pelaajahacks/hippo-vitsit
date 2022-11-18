<script setup lang="ts">

</script>

<template>
    <main class="">
        <div class="hipposanoobox">
            <div class="hippo-vitsi">
                <b>{{hippoVitsi}}</b>
            </div>
        </div>
    </main>
    
</template>

<script lang="ts">
export default {
  name: 'Vitsi',
  data() {
    return {
        hippoVitsi: "Mitä hippo osti kaupasta? 4gb muistitikun ja munkin"
    }
  }
};
</script>

<style scoped>
    .main {
        display: flex;
    }
    .hipposanoobox {
        background-color: #494949;
        width: 90vw;
        height: 30vw;
        margin: 0 auto;
        display: flex;
        border-radius: 6px;
    }

    .hippo-vitsi {
        font-size: 6vw;
        font-family: Sono;
        text-align: center;
        margin: auto auto;
        color: #eee;
    }
</style>
