<template>
    <div :class="alert" v-if="showAlert">
        <slot></slot>

        <button
            @click="onClick()"    
        >
            X
        </button>
    </div>
</template>

<script>
export default {
    props: {
        variant: {
            type: String,
            default: 'alert'
            }
    },
    data() {
        return {
            showAlert: true
        }
    },
    methods: {
        onClick() {
            this.$emit('close');
            this.showAlert = false
            console.log('clicou')
        }
    },
    computed: {
        alert() {
                return this.variant ? `alert alert-${this.variant}` : ''
            }
        }
    }
</script>

<style scoped>
    .alert {
        background-color: gray;
        border-radius: 10px;
        padding: 5px;
    }

    .alert-success {
        background-color: green;
        color: #fff;
    }

    .alert-danger {
        background-color: red;
        color: #fff;
    }
</style>

