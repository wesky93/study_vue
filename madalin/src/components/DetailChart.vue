<template>
  <table>
    <tr>
      <td>
        <input-box v-model="a"></input-box>
      </td>
      <td>
        <input-box v-model="b"></input-box>
      </td>
      <td>
        <input-box v-model="c"></input-box>
      </td>
    </tr>
    <tr>
      <td>
        <input-box v-model="d"></input-box>
      </td>
      <td>
        <input-box :value="$attrs.link" readonly></input-box>
      </td>
      <td>
        <input-box v-model="e"></input-box>
      </td>
    </tr>
    <tr>
      <td>
        <input-box v-model="f"></input-box>
      </td>
      <td>
        <input-box v-model="g"></input-box>
      </td>
      <td>
        <input-box v-model="h"></input-box>
      </td>
    </tr>
  </table>
</template>

<script>
    import InputBox from "./InputBox";

    export default {
        components: {InputBox,},
        props:['text'],
        data() {
            return {
                a: "",
                b: "",
                c: "",
                d: "",
                e: "",
                f: "",
                g: "",
                h: "",
            }
        },
    }
</script>

<style scoped>
  table {
    border-collapse: collapse;
  }

  th, td {
    border: 1px solid #444444;
    padding: 0px !important;
  }
</style>
