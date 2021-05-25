<template>
    <button :class="buttonClasses" @click="handleClick" ref="button" />
</template>

<script>
    export default {
        name: 'SimonButton',
        props: {
            idx: {
                type: Number,
                required: true,
            },
            color: {
                type: String,
                required: true,
            },
            name: {
                type: String,
                required: true,
            },
        },
        data: () => ({
            sound: null,
        }),
        created() {
            const path = require(`@/assets/sounds/${this.name}`);
            this.sound = new Audio(path);
        },
        computed: {
            buttonClasses() {
                return ['simon-button', this.color];
            },
        },
        methods: {
            play() {
                this.sound.play();
                this.$refs.button.classList.add('active');
                setTimeout(() => {
                    this.$refs.button.classList.remove('active');
                }, 400);
            },
            handleClick() {
                this.play();
                this.$emit('click', this.idx);
            },
        },
    };
</script>

<style scoped lang="sass">
    .simon-button
        width: inherit
        height: inherit
        border: none
        &:focus
            box-shadow: inset 0px 0px 50px 0 rgba(0, 0, 0, 0.25)
            outline: none
        &.blue
            background-color: var(--blue-color)
            &.active
                background-color: var(--blue-color-active)
            &:hover
                background-color: var(--blue-color-hover)
        &.red
            background-color: var(--red-color)
            &.active
                background-color: var(--red-color-active)
            &:hover
                background-color: var(--red-color-hover)
        &.yellow
            background-color: var(--yellow-color)
            &.active
                background-color: var(--yellow-color-active)
            &:hover
                background-color: var(--yellow-color-hover)
        &.green
            background-color: var(--green-color)
            &.active
                background-color: var(--green-color-active)
            &:hover
                background-color: var(--green-color-hover)
</style>
