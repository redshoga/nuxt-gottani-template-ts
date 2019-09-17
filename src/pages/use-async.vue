<template>
  <div>
    <h1>Use Async + Axios Sample</h1>
    <div>
      YES or NO: {{ yesOrNo.answer }}
    </div>
    <div>
      <img :src="yesOrNo.image">
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import { axiosClient } from '../plugins/axios'

interface YesOrNo {
  answer: string,
  forced: boolean,
  image: string
}

interface AsyncData {
  yesOrNo: YesOrNo
}

export default Vue.extend({
  async asyncData(): Promise<AsyncData> {
    const { data } = await axiosClient.get<YesOrNo>('https://yesno.wtf/api')
    return {
      yesOrNo: data
    }
  }
})
</script>
