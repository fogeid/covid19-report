<template>
    <div id="app">
        <header class="header">
            <app-header />
        </header>
        <main class="container-fluid main">
            <div>
                <app-select />
            </div>
            <div>
                <!-- <app-card /> -->
            </div>
        </main>
        <footer class="footer">
            <app-footer />
        </footer>
    </div>
</template>


<script>
import Header from '@/components/template/Header.vue';
import Select from '@/components/template/Select.vue';
// import Card from '@/components/template/Card.vue';
import Footer from '@/components/template/Footer.vue';

export default {
    name: 'Home',
    components:{
        'app-header': Header,
        'app-select': Select,
        // 'app-card': Card,
        'app-footer': Footer
    }
}
</script>

<style src="./style.scss" lang="scss" scoped />