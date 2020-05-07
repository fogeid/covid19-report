<template>
    <div id="app">
        <div>
            <header>
                <app-header />                
            </header>
        </div>
        <div class="container-fluid">
            <div>
                <app-select />
            </div>
            <div>
                <!-- <app-card /> -->
            </div>
        </div>
        <!-- <app-footer /> -->
    </div>
</template>


<script>
import Header from '@/components/template/Header.vue';
import Select from '@/components/template/Select.vue';
// import Card from '@/components/template/Card.vue';
// import Footer from '@/components/template/Footer.vue';

export default {
    name: 'Home',
    components:{
        'app-header': Header,
        'app-select': Select,
        // 'app-card': Card,
        // 'app-footer': Footer
    }
}
</script>

<style src="./style.scss" lang="scss" scoped />