<template>
  <q-dialog :model-value="modelValue" @update:mode-value="val => $emit('update:modeValue', val)">
      <q-card :style="{width: '400px'}">
        <q-card-section class="flex justify-end">
          <q-btn icon="close" flat round dense v-close-popup/>
        </q-card-section>

        <q-card-section>
          <SignInForm />
        </q-card-section>
      </q-card>
    </q-dialog>
</template>

<script setup>
import SignInForm from './SignInForm.vue';
import SignUpForm from './SignUpForm.vue';
import FindPasswordForm from './FindPasswordForm.vue';


defineProps({
  modelValue: {
   type: Boolean,
   default: false 
  }
})
defineEmits(['update:modeValue'])
</script>

<style lang="scss" scoped>

</style>