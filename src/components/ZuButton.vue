<template>
    <button :type="type" class="btn" :class="('zu-button ' + className)" @click="$emit('click')">
        <span class="icon material-icons" v-if="icon">
            {{ icon }}
        </span>
        <span class="mt-5">
            {{ label }}
        </span>
    </button>
</template>

<script lang="ts">

import { ref } from "vue";
import type { PropType, ButtonHTMLAttributes } from 'vue';

export default {
    name: 'ZuButton',
    props: {
        label: {
            type: String,
            required: true,
        },
        icon: {
            type: String,
            required: false,
        },
        class: {
            type: String,
            required: false,
            default: ''
        },
        type: {
            type: String as PropType<ButtonHTMLAttributes['type']>,
            required: false,
            default: "button"
        }
    },
    setup(props) {
        const className = ref(props.class);
        return { className };
    }
}
</script>