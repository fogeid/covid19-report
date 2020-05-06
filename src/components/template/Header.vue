<template>
    <div>
        <div class="header">
            <a href="#"><img :src="logo" alt="Covid-19 Brazil"></a>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            logo: 'logo.png',
        }
    }
}
</script>

<style src="./header.scss" lang="scss">