<template>
    <div class="fixed-header">
        <div class="container">
          Header Here....
        </div>
    </div>
</template>


<script>
export default {
  data() {
    return {
    };
  },
};
</script>

<style scoped>
.container{
        width: 80%;
        margin: 0 auto; /* Center the DIV horizontally */
        justify-content: center;
        text-align: center;
    }
    .fixed-header{
        width: 100%;
        position: fixed;        
        background: #333;
        padding: 10px 0;
        color: #fff;
        left: 0;
        top: 0;

    }
</style>