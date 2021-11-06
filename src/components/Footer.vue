<template>
    <div class="footer">
        <span>
            {{ new Date().toLocaleDateString() }} &copy;
        </span>
    </div>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style scoped>
    
    .footer {
        height: 50px;
        background-color: rgb(225, 225, 225);
        box-sizing: border-box;
        padding: 5px 15px;
    }

</style>