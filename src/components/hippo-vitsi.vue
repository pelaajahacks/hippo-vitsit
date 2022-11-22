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
import axios from 'axios'
export default {
  name: 'Vitsi',
  methods: {
    getHippoVitsi() {
        axios.get('https://api.segso.net/hippo-vitsi')
            .then(response => {
                // handle success
                if(this.hippoVitsi != response.data) {
                    this.hippoVitsi = response.data
                }
                else {
                    this.getHippoVitsi()
                }
                return "Success"
            })
            .catch(error => {
                // handle error
                return "Error"
            })
    },
  },
  data() {
    
    return {
        hippoVitsi: null
    }
  },
  mounted() {
    this.getHippoVitsi()
    setInterval(() => this.getHippoVitsi(), 10000)
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
