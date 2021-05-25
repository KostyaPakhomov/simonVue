<template>
    <div id="app">
        <Simon />
    </div>
</template>

<script>
    import Simon from '@/components/Simon';

    export default {
        name: 'App',
        components: {
            Simon,
        },
    };
</script>

<style lang="sass">
    *
        box-sizing: border-box
    html
        color: var(--font-color)
        font-size: 16px
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif
    body
        padding: 0
        margin: 0
        background-color: antiquewhite
    \:root
        --font-color: hsl(0, 1%, 48%)
        --heading-color: hsl(0, 0%, 4%)
        --red-color: hsl(5, 78%, 44%)
        --red-color-active: hsl(6, 60%, 59%)
        --red-color-hover: hsl(7, 92%, 49%)
        --blue-color: hsl(205, 59%, 38%)
        --blue-color-active: hsl(205, 53%, 36%)
        --blue-color-hover: hsl(204, 88%, 56%)
        --yellow-color: hsl(48, 68%, 40%)
        --yellow-color-active: hsl(48, 57%, 55%)
        --yellow-color-hover: hsl(47, 89%, 51%)
        --green-color: hsl(144, 61%, 35%)
        --green-color-active: hsl(145, 37%, 49%)
        --green-color-hover: hsl(144, 92%, 52%)
    #app
        display: flex
        justify-content: center
        align-items: center
        min-height: 100vh
        padding: 30px

</style>
