<template>
    <button>
        <slot></slot>
    </button>
</template>
<style scoped>
button {
    padding: 10px 30px;
    background: linear-gradient(45deg, #c31432, #240b36);
    color: white;
    border: 0;
    margin-right: 1em;
    font-weight: bolder;
    opacity: .8;
}

button:hover {
    opacity: 1;
}
</style>