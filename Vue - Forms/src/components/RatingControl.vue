<template>
    <ul>
        <li :class="{active: modelValue === 'poor'}"><button type="button" @click="activate('poor')">Poor</button></li>
        <li :class="{active: modelValue === 'average'}"><button type="button" @click="activate('average')">Average</button></li>
        <li :class="{active: modelValue === 'great'}"><button type="button" @click="activate('great')">Great</button></li>
    </ul>
</template>

<style scoped>
    ul {
        list-style-type: none;
        margin: 0.5rem 0;
        padding: 0;
        display: flex;
    }

    li {
        margin: 0 1rem;
        border: 1px solid #ccc;
        padding: 1rem;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    button {
        font: inherit;
        border: none;
        background-color: transparent;
        cursor: pointer;
    }

    .active {
        border-color: #a00078;
    }

    .active button {
        color: #a00078;
    }
</style>

<script>
    export default {
        props: ['modelValue'],
        emits: ['update:modelValue'],
        data() {
            return {
                activeOption: this.modelValue
            }
        },

/*         computed: {
            activeOption() {

            }
        }, */

        methods: {
            activate(option) {
                this.activeOption = option;
                this.$emit('update:modelValue', option)
            }
        }
    } 
</script>