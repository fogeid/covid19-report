<template>
    <div>
        <div class="card">
            <h2>{{ title }}</h2>
            <h1>{{ casos || mortes || curados || suspeitos }}</h1>
        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    props: ["title", "casos", "mortes", "curados", "suspeitos"]    
}
</script>

<style src="./card.scss" lang="scss">