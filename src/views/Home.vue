<script lang="ts" setup>
import {
  $navigateTo
} from 'nativescript-vue';
import ElementSizeView from "./ElementSizeView.vue";
import ColorModeView from "./ColorModeView.vue";
import EventListenerView from "./EventListenerView.vue";
import RootLayoutView from './RootLayoutView.vue';
import ScreenOrientationView from './ScreenOrientationView.vue';
import CustomPage from '@/components/CustomPage.vue';
import KeyboardView from './KeyboardView.vue';
import BreakpointsView from './BreakpointsView.vue';
import ClipboardView from './ClipboardView.vue';
import Icon from '~/components/Icon.vue';
import { useColorPalette } from '@nativescript-use/vue';
import { Patelle } from '~/data';

const { palette } = useColorPalette<string, Patelle>()

const views = [
  { title: "Clipboard", viewComponent: ClipboardView, icon: "assignment" },
  { title: "Element Size", viewComponent: ElementSizeView, icon: "straighten" },
  { title: "Color Mode", viewComponent: ColorModeView, icon: "palette" },
  { title: "Event Listener", viewComponent: EventListenerView, icon: "hearing" },
  { title: "Keyboard", viewComponent: KeyboardView, icon: "keyboard" },
  { title: "Breakpoints", viewComponent: BreakpointsView, icon: "web_stories" },
  { title: "Root Layout", viewComponent: RootLayoutView, icon: "flip_to_back" },
  { title: "Orientation", viewComponent: ScreenOrientationView, icon: "screen_rotation_alt" },
]

</script>

<template>
  <Frame :backgroundColor="palette?.colors.bg">
    <CustomPage>
      <ScrollView>
        <StackLayout ref="test" class="px-2">
          <Label text="NativeScript-VueUse APP" class="text-2xl font-bold mt-6 ml-2" />

          <FlexboxLayout class="flex-wrap mt-8">
            <StackLayout class="w-[50%] p-2 " v-for="(item, i) in views" :key="i" @tap="$navigateTo(item.viewComponent)">
              <FlexboxLayout class="bg-variant p-2  py-4 rounded-lg flex-col">
                <Icon width="32" class="" :icon="item.icon"></Icon>
                <Label :text="item.title" class="text-xl font-bold mt-4" textWrap="true" style="line-height: 1;" />
              </FlexboxLayout>
            </StackLayout>

          </FlexboxLayout>
        </StackLayout>
      </ScrollView>
    </CustomPage>
  </Frame>
</template>

<style>

</style>
