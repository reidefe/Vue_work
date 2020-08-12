<template>
  <div class="hello">
 
      <v-data-table 
       :headers="tableItems"
        :items='allCars'
        :items-per-page='15'
        class="elevation-1">       
        
      </v-data-table>
      <!--      
      <table>
        <tr>
          <th>Name</th>
          <th>Miles_per_Gallon</th>
          <th>Cylinders</th>
          <th>Displacement</th>
          <th>Horsepower</th>
          <th>Weight_in_lbs</th>
          <th>Acceleration</th>
          <th>Year</th>
          <th>Origin</th>
        </tr>
        <tr  v-for="car in allCars" v-bind:key="car">
          <th> 
            <td>{{car.Name}}</td>
          </th>
          <th>
            <td>{{car.Miles_per_Gallon}}</td>
          </th>
          <th>
            <td>{{car.Cylinders}}</td>
          </th>
          <th>
            <td>{{car.Displacement}}</td>

          </th>
          <th>
            <td>{{car.Horsepower}}</td>
          </th>
          <th>
             <td>{{car.Weight_in_lbs}}</td>
          </th>
          <th>
            <td>{{car.Acceleration}}</td>
          </th>
          <th>
            <td>{{car.Year}}</td>
          </th>
          <th>
            <td>{{car.Origin}}</td>
          </th>
        </tr>
         <tr  v-for="car in carsJson2" v-bind:key="car">
          <th> 
            <td>{{car.Name}}</td>
          </th>
          <th>
            <td>{{car.Miles_per_Gallon}}</td>
          </th>
          <th>
            <td>{{car.Cylinders}}</td>
          </th>
          <th>
            <td>{{car.Displacement}}</td>

          </th>
          <th>
            <td>{{car.Horsepower}}</td>
          </th>
          <th>
             <td>{{car.Weight_in_lbs}}</td>
          </th>
          <th>
            <td>{{car.Acceleration}}</td>
          </th>
          <th>
            <td>{{car.Year}}</td>
          </th>
          <th>
            <td>{{car.Origin}}</td>
          </th>
        </tr>  
         <tr  v-for="car in carsJson3" v-bind:key="car">
          <th> 
            <td>{{car.Name}}</td>
          </th>
          <th>
            <td>{{car.Miles_per_Gallon}}</td>
          </th>
          <th>
            <td>{{car.Cylinders}}</td>
          </th>
          <th>
            <td>{{car.Displacement}}</td>

          </th>
          <th>
            <td>{{car.Horsepower}}</td>
          </th>
          <th>
             <td>{{car.Weight_in_lbs}}</td>
          </th>
          <th>
            <td>{{car.Acceleration}}</td>
          </th>
          <th>
            <td>{{car.Year}}</td>
          </th>
          <th>
            <td>{{car.Origin}}</td>
          </th>
        </tr> 
         <tr  v-for="car in carsJson4" v-bind:key="car">
          <th> 
            <td>{{car.Name}}</td>
          </th>
          <th>
            <td>{{car.Miles_per_Gallon}}</td>
          </th>
          <th>
            <td>{{car.Cylinders}}</td>
          </th>
          <th>
            <td>{{car.Displacement}}</td>

          </th>
          <th>
            <td>{{car.Horsepower}}</td>
          </th>
          <th>
             <td>{{car.Weight_in_lbs}}</td>
          </th>
          <th>
            <td>{{car.Acceleration}}</td>
          </th>
          <th>
            <td>{{car.Year}}</td>
          </th>
          <th>
            <td>{{car.Origin}}</td>
          </th>
        </tr>  
         <tr  v-for="car in carsJson5" v-bind:key="car">
          <th> 
            <td>{{car.Name}}</td>
          </th>
          <th>
            <td>{{car.Miles_per_Gallon}}</td>
          </th>
          <th>
            <td>{{car.Cylinders}}</td>
          </th>
          <th>
            <td>{{car.Displacement}}</td>

          </th>
          <th>
            <td>{{car.Horsepower}}</td>
          </th>
          <th>
             <td>{{car.Weight_in_lbs}}</td>
          </th>
          <th>
            <td>{{car.Acceleration}}</td>
          </th>
          <th>
            <td>{{car.Year}}</td>
          </th>
          <th>
            <td>{{car.Origin}}</td>
          </th>
        </tr>  
       
      </table>       --->
    
  </div>
</template>

<script>
import cars1 from '../data/cars-1.json'
import cars2 from '../data/cars-2.json'
import cars3 from '../data/cars-3.json'
import cars4 from '../data/cars-4.json'
import cars5 from '../data/cars-5.json'
import Vuetify from 'vuetify'
import Vue from 'vue'
import 'vuetify/dist/vuetify.min.css'
import lod from 'lodash'
Vue.use(Vuetify)
const allCars =  lod.concat(cars1, cars2, cars3, cars4, cars5)



export default {
  name: 'HelloWorld',
  //component: getAllCars,
  data(){
    return{
    allCars,  
      
     
      tableItems: [
        {
          text: 'Name',
          align: 'start',
          value: 'Name'
        },
        { text: "Miles_per_Gallon", value: "Miles_per_Gallon"},
        { text: "Cylinders", value: "Cylinders"},
        { text: "Displacement", value: "Displacement"},
        { text: "Horsepower", value: "Horsepower"},
        { text: "Weight_in_lbs", value: "Weight_in_lbs"},
        { text: "Acceleration", value: "Acceleration"},
        { text: "Year", value: "Year"},
        { text: "Origin", value: "Origin"}
      ]
    }
  },
  mounted: function(){
    this.getAllCars
  },
  method:{  
  getAllCars: async function (){
  let res = await fetch(allCars);
  let cars = await res.json
  return this.allCars = cars
}  
    
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td, th {
  border:  #dddddd;
  text-align: left;
  padding: 8px;
}

tr:nth-child(even) {
  background-color: #dddddd;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
