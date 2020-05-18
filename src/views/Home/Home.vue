<template>
    <div id="app">
        <header class="header">
            <app-header />
        </header>
        <main class="container-fluid main">
            <section class="buscar">
                <app-select @dados="getDados" />
            </section>
            <section class="cards">
                <app-card class="cards__item" :casos="regioes.cases" title="Casos Confirmados" />
                <app-card class="cards__item" :mortes="regioes.deaths" title="Mortes" />
                <app-card class="cards__item" :curados="regioes.refuses" title="Curados" />
                <app-card class="cards__item" :suspeitos="regioes.suspects" title="Suspeitos" />
            </section>
        </main>
        <footer class="footer">
            <app-footer />
        </footer>
    </div>
</template>

<script>
import Header from '@/components/template/Header.vue';
import Select from '@/components/template/Select.vue';
import Card from '@/components/template/Card.vue';
import Footer from '@/components/template/Footer.vue';

export default {
    name: 'Home',
    components:{
        'app-header': Header,
        'app-select': Select,
        'app-card': Card,
        'app-footer': Footer
    },
    data() {
        return {
            regioes: [],
        }
    },
    methods: {
        getDados(event) {
            this.regioes = event;
            console.log(this.regioes);
        }
    }
}
</script>

<style src="./style.scss" lang="scss" scoped />