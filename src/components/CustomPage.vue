<script lang="ts" setup>
import { useColorPalette } from '@nativescript-use/vue';
import { Patelle } from '~/data';

const { palette } = useColorPalette<string, Patelle>()
</script>

<template>
  <Page actionBarHidden="true" :androidStatusBarBackground="palette?.colors.bg">
    <slot></slot>
  </Page>
</template>

