<template>
    <div class="component">
        <div id="table">

        <!-- Table Dates -->
            <table class="gridtable">
            <tr>
                <th class="round_1"> 1st ROUND </th>
                <th class="round_2 "> 2nd ROUND </th>
                <th class="round_3"> SWEET 16 </th>
                <th class="round_4"> ELITE EIGHT </th>
                <th class="round5"> FINAL FOUR </th>
                <th class="round_6"> CHAMPION </th>
                <th class="round_5"> FINAL FOUR </th>
                <th class="round_4"> ELITE EIGHT </th>
                <th class="round_3"> SWEET 16 </th>
                <th class="round_2"> 2nd ROUND </th>
                <th class="round_1"> 1st ROUND </th>
            </tr>
            <tr>
                <td> March 21-22 </td>
                <td> March 23-24 </td>
                <td> March 28-29 </td>
                <td> March 30-31 </td>
                <td> April 6 </td>
                <td> April 8 </td>
                <td> April 6 </td>
                <td> March 30-31 </td>
                <td> March 28-29 </td>
                <td> March 23-24 </td>
                <td> March 21-22 </td>
            </tr>
            </table>
        </div>
    </div>
</template>

<script>
    export default{
        props: {
            
        },
        methods:{
            
        }
    }
</script>

<style scoped>
    table.gridtable {
    font-size: 11px;
    color: #333333;
    border-width: 1px;
    border-color: #fff;
    border-collapse: collapse;
  }
  table.gridtable th {
    background-color: #b3d4ef;
    padding: 8px;
    width: 97px;
    border: 1px solid #fff;
  }
  table.gridtable td {
    border-width: 1px;
    padding: 8px;
    border-style: solid;
    border-color: #fff;
    background-color: #ffffff;
    text-align: center;
  }
  table.gridtable td.title {
    background: #ccc;
    font-weight: bold;
  }
</style>
