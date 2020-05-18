<template>
    <div>
        <div class="card">
            <h2>{{ title }}</h2>
            <h1>36512</h1>
        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    props: ["title", "statistic", "regiaoSelecionada"]    
}
</script>

<style src="./card.scss" lang="scss">