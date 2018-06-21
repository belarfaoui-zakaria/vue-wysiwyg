<template>
    <div>
        <button v-for="k in fonts " :key="k.size" :data-value="k.size" style="margin-right:2px;display: inline-block;font-size:10px;width: 32px; height: 24px; line-height: 1.2; border-radius: 0.25rem;border: 1px solid transparent;text-align: center; white-space: nowrap; vertical-align: middle; user-select:  none;"    @click="insertHeading">
          {{k.pixels}}
        </button>
    </div>
</template>

<script>

import bus from '../bus.js';

export default {
    title: "headings",
    description: "Font size",
    icon: '<svg viewBox="0 0 32 32" xmlns="http://www.w3.org/2000/svg"><path d="M2 16h12v4h-4v12h-4v-12h-4zM30 8h-7.867v24h-4.266v-24h-7.867v-4h20z"></path></svg>',
    data () {
      return {
        fonts: [
          {size: 1, pixels: '12px'},
          {size: 2, pixels: '14px'},
          {size: 3, pixels: '16px'},
          {size: 4, pixels: '20px'},
          {size: 5, pixels: '24px'},
          {size: 6, pixels: '30px'},
          {size: 7, pixels: '36px'}
        ]
      }
    },
    methods: {
        insertHeading(e){
            this.$parent.closeDashboard();
            this.$emit("exec", "fontSize", e.target.dataset.value);
        }
    }
};

</script>
