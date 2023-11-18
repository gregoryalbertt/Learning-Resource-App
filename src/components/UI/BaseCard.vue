<template>
    <div>
        <slot></slot>
    </div>
</template>

<script>
export default {

}
</script>

<style scoped>
div {
    margin: 1rem auto;
    max-width: 40rem;
    border-radius: 12px;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    padding: 1rem;
    margin-left: 1rem;
    margin-right: 1rem;
}

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>