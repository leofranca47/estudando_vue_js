<template>
    <div :class="alert">
        <slot></slot>
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
        text-align: center;
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

