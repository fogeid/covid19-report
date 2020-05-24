<template>
    <div>
        <div class="select">      
            <div class="seletor d-flex justify-content-center">
                <select name="regions" id="regions"  class="form-control col-md-6" v-model="regionSelected">
                    <option disabled value="">Selecione o estado</option>
                    <option v-for="(value, index) in regions.data"                          
                            :key="index"
                            :value="value.state">
                            {{ value.state }}                            
                    </option>
                </select>
            </div>     
            <div>
                <h1 class="title"># {{ regionSelected }} #</h1>
            </div>                 
        </div>
    </div>
</template>

<script>
export default {
    name: "Select",
    data() {
        return {
            regions: {},
            state: '',
            regionSelected: ''
        }
    },
    created() {
        this.getData();
    },  
    methods: {
        getData() {
            fetch("https://covid19-brazil-api.now.sh/api/report/v1")
            .then(res => res.json())
            .then(res => {
                this.regions = res;                           
            });
        }
    },
    watch: {
        regionSelected(value) {
            this.state = this.regions.data.find((es) => es.state === value);
            this.$emit("data", this.state);
        }
    }
}
</script>

<style src="./select.scss" lang="scss">