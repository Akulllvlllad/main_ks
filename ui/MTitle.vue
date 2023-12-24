<template>
    <component :is="tag">
        <slot />
    </component>


</template>

<script>
export default {
    name: 'MTitle',
    props: { 
        tag: { default: 'h2', type: String }
    }    
}
</script>

<style scoped>
h2{
    
}
</style>