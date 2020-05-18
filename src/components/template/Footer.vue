<template>
    <div>
        <div class="footer">
            <p class="footer__title">2020 © Developed by <a class="footer__title__link" :href="github" target="_blank">Diego Batista</a></p>
        </div>
    </div>
</template>

<script>
export default {
    name: "Footer",
    data() {
        return {
            github: 'https://github.com/fogeid',
        }
    },
}
</script>

<style src="./footer.scss" lang="scss">