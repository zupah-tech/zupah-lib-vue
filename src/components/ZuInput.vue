<template>
    <div :class="className" :for="id" class="zu-input">

        <label :for="id">
            {{ label }}
        </label>

        <input @input="updateValue" :type="type" :name="name" :id="id" :value="modelValue" :maxlength="maxlength"
            @change="onChange" @focus="onFocus" @blur="onBlur" @focusout="onFocusOut" autocomplete="false" />

        <div v-if="maxlength > 0 && count" class="count">{{ modelValue?.length }} de {{ maxlength }}</div>

    </div>
</template>

<script lang="ts">

import { ref } from "vue";


export default {
    name: 'ZuInput',
    props: {
        label: {
            type: String,
            required: true,
        },
        modelValue: {
            type: String,
            required: false,
        },
        name: {
            type: String,
            required: false,
        },
        id: {
            type: String,
            required: false,
            default: 'zu-in-id-' + Math.random()
        },
        type: {
            type: String,
            required: true,
        },
        class: {
            type: String,
            required: false,
        },
        maxlength: {
            type: Number,
            required: false,
            default: 250
        },
        count: {
            type: Boolean,
            required: false,
            default: false
        }
    },
    setup(props, context) {
        const updateValue = (event: any) => {
            context.emit('update:modelValue', event.target.value);
        }

        const className = ref<string | undefined>(props.class);
        return { updateValue, className };
    },
    methods: {
        onChange(event: any) {
            const value = event.target.value;

            if (value) {
                this.className = this.addClass(this.className, 'has-value');
            } else {
                this.className = this.removeClass(this.className, 'has-value');
            }
        },
        onFocusOut() {
        },
        onFocus() {
            this.$emit('focus');
            this.className = this.addClass(this.className, 'has-focus');
        },
        onBlur() {
            this.$emit('blur');
            this.className = this.removeClass(this.className, 'has-focus');
        },
        addClass(value: string | undefined, name: string): string {
            let result = value + '';
            if (result.indexOf(name) == -1) {
                result = result + ' ' + name;
            }
            return result;
        },
        removeClass(value: string | undefined, name: string): string {
            let result = value + '';
            if (result.indexOf(name) > -1) {
                result = result.replace(name, '').trim();
            }
            return result;
        }
    }
}
</script>