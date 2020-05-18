<template>
    <div>
        <div class="select">      
            <div class="seletor d-flex justify-content-center">
                <select name="regioes" id="regioes" class="form-control col-md-6" v-model="regiaoSelecionada">
                    <option disabled value="">Selecione o estado</option>
                    <option v-for="(valor, index) in regioes.data"                            
                            :key="index"
                            :value="valor.state">
                            {{ valor.state }}                            
                    </option>
                </select>
            </div>     
            <div>
                <h1 class="title"># {{ regiaoSelecionada }} #</h1>
            </div>                 
        </div>
    </div>
</template>

<script>
export default {
    name: "Select",
    data() {
        return {
            regioes: {},
            estado: '',
            chave: Number,
            regiaoSelecionada: ''
        }
    },
    created() {
        this.getDados();
    },  
    methods: {
        getDados() {
            fetch("https://covid19-brazil-api.now.sh/api/report/v1")
            .then(res => res.json())
            .then(res => {
                this.regioes = res;
                this.$emit("dados", this.regioes.data);                
            });
        }
    },
    watch: {
        regiaoSelecionada(valor) {
            this.estado = this.regioes.data.find((es) => es.state === valor);
        }
    }
}
</script>

<style src="./select.scss" lang="scss">