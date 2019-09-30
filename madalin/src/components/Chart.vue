<template>
  <div>
    <h1>{{name}}</h1>
  <div id="chart">
    <template v-for="(val,index) in link">
        <table id="main" v-if="index === 4">
          <tr>
            <td>
              <input-box v-model="link[0]"></input-box>
            </td>
            <td>
              <input-box v-model="link[1]"></input-box>
            </td>
            <td>
              <input-box v-model="link[2]"></input-box>
            </td>
          </tr>
          <tr>
            <td>
              <input-box v-model="link[3]"></input-box>
            </td>
            <td>
              <input-box placholder="제목을 입력 하세요" v-model="title"></input-box>
            </td>
            <td>
              <input-box v-model="link[5]"></input-box>
            </td>
          </tr>
          <tr>
            <td>
              <input-box v-model="link[6]"></input-box>
            </td>
            <td>
              <input-box v-model="link[7]"></input-box>
            </td>
            <td>
              <input-box v-model="link[8]"></input-box>
            </td>
          </tr>
        </table>
      <detail-chart :link="val" v-if="index !== 4"></detail-chart>
    </template>

  </div>
  </div>
</template>

<script>
    import DetailChart from "./DetailChart";
    import InputBox from "./InputBox";
    export default {
        components: {DetailChart,InputBox},
        data(){
            return {
                title:"",
                link:["a", "b", "c","d","","e","f","g","h"],
            }
        },
        computed:{
            name(){
                if (this.title)  return this.title;
                else return  "만다라트 차트";
            }
        }
    }
</script>

<style scoped>
  #chart{
    display: inline-grid;
    width: 630px;
    grid-template-columns: repeat(3, 210px);
    grid-auto-rows: 210px;

  }
  #main  {
    border-collapse: collapse;
  }

  th, td {
    border: 1px solid #444444;
    padding: 0px !important;
  }
</style>
