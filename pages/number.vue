<template lang="pug">
  v-form
    v-container
      v-row
        input-number(@setNumber="(value) => (first = value)")
        input-number(@setNumber="(value) => (second = value)")
        input-number(@setNumber="(value) => (third = value)")
        input-number(@setNumber="(value) => (fourth = value)")
      v-btn.mt-5.mb-10(
        color="accent"
        elevation="2"
        x-large
        @click="execute"
      ) 計算実行
      v-row.mb-5 以下、10になる答え表示
      v-row(
        v-for="(result, index) in results"
        :key="`result-${index}`"
      )
        v-col(
          cols="1"
          md="3"
        ) {{ result }}
</template>

<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api'
import { Big } from 'big.js'
import InputNumber from '~/components/atoms/InputNumber.vue'

export default defineComponent({
  components: {
    InputNumber
  },

  setup() {
    // 画面入力値
    const first = ref<number>(0)
    const second = ref<number>(0)
    const third = ref<number>(0)
    const fourth = ref<number>(0)

    // 10になる答えを入れる配列
    const results = ref<Array<String>>([])

    // "計算実行"ボタン押下時に実行されるメソッド

    // 4つの数字の順番を考慮(24通り)
    // 全て計算する(64通り)
    const numbers = [first.value, second.value, third.value, fourth.value];
    console.log(numbers);


    // 10になる数字だけ取り出す

    // ここでresultsに10になる答えを入れる
    // 小数点の計算などでバグる可能性あるので、big.jsをインストール済です
    // https://github.com/MikeMcl/big.js/
    const execute = () => {
      results.value = []
      const f: Big = Big(first.value)
      const s: Big = Big(second.value)
      const t: Big = Big(third.value)
      results.value.push(String(f.div(s).times(t).toFixed(0)))
    }

    return {
      first,
      second,
      third,
      fourth,
      results,
      execute
    }
  }
})
</script>
