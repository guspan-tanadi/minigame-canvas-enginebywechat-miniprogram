<script lang="ts">
import { defineComponent } from "vue";
import TabView from "primevue/tabview";
import TabPanel from "primevue/tabpanel";

// @ts-ignore
import RichText from "./richtext.vue";
// @ts-ignore
import BitMapText from "./bitmaptext.vue";
// @ts-ignore
import Text from "./text.vue";
// @ts-ignore
import HelloWorld from "./helloworld.vue";
// @ts-ignore
import RankList from "./ranklist.vue";
// @ts-ignore
import Tween from "./tween.vue";
// @ts-ignore
import CanvasDemo from "./canvas.vue";
// @ts-ignore
import Loading from "./loading.vue";
// @ts-ignore
import Invite from "./invite.vue";
// @ts-ignore
import Rotate from "./rotate.vue";
// @ts-ignore
import Button from "./button.vue";
// @ts-ignore
import InsertElement from "./insertElement.vue";


export default defineComponent({
  components: {
    TabView,
    TabPanel,

    HelloWorld,
    RichText,
    BitMapText,
    Text,
    RankList,
    Tween,
    CanvasDemo,
    Loading,
    Invite,
    // Rotate,
    Button,
    InsertElement,
  },
  data() {
    return {
      isDev: true,

      tabindex: 3,
    };
  },
  mounted() {
    const panel = this.$refs[`panel__` + this.tabindex];
    this.$nextTick(() => {
      // @ts-ignore
      panel?.init();
    });
  },
  methods: {
    demoChangeHandler(event: any) {
      const Layout = (window as any).Layout;

      Layout.clearAll();

      const panel = this.$refs[`panel__` + event.index];
      this.$nextTick(() => {
        // @ts-ignore
        panel.init();
      });
    },
  },
});
</script>
<template>
  <TabView
    :scrollable="true"
    :activeIndex="tabindex"
    @tab-change="demoChangeHandler"
  >
    
    <TabPanel header="HelloWorld">
      <HelloWorld ref="panel__0" />
    </TabPanel>
    <TabPanel header="RichText">
      <RichText ref="panel__1" />
    </TabPanel>
    <TabPanel header="BitMapText">
      <BitMapText ref="panel__2" />
    </TabPanel>
    <TabPanel header="Text">
      <Text ref="panel__3" />
    </TabPanel>
    <TabPanel header="RankList">
      <RankList ref="panel__4" />
    </TabPanel>
    <TabPanel header="Tween">
      <Tween ref="panel__5" />
    </TabPanel>
    <TabPanel header="Canvas">
      <CanvasDemo ref="panel__6" />
    </TabPanel>
    <TabPanel header="Loading">
      <Loading ref="panel__7" />
    </TabPanel>
    <TabPanel header="Invite">
      <Invite ref="panel__8" />
    </TabPanel>
    <TabPanel header="Button">
      <Button ref="panel__9" />
    </TabPanel>
    <TabPanel header="InsertElement">
      <InsertElement ref="panel__10" />
    </TabPanel>
  </TabView>
</template>
