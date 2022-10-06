<template>
  <div id="app">
    <h1> Binding</h1>
     <h2> 1. Binding text </h2>
   <h3> Hii !! This is {{  name}}{{lastname}}'s Practice Page</h3> 
   <h3 v-text="directive"></h3>

   <h2> 2.Binding HTML</h2>
   <h3 v-text =" bindingHtml">  </h3>
   <h3 v-html =" bindingHtml">   </h3>

   <h3 v-bind:id="placeholderforID">3.  The Binding of attributes(ID)</h3>
   
  <h2> 3. Class Binding </h2>
   <button  class="buttonHolder"> Static class Binding HTML </button><br>
   <button  v-bind:class="buttonHolderVue"> class binding using directive  </button>
   <h3 v-bind:class ="['trueClass','trueClass2']"> Class binding using Array of classes</h3>

   <h2>4. Conditional Binding </h2>
   <h3>1. Using array for classes</h3>
   <button type="radio" v-bind:class= " 'enabled' ?   ['trueClass','trueClass2'] : ['falseClass' ,'falseClass'] "> VUEarray </button> 
   <h3>2. Using objects for classes</h3>
  <button v-bind:class="{ trueClass:enabled,
   trueClass2:enabled,
   falseClass:!enabled,
   falseClass2:!enabled }"> Vue buttton using objectsS</button> 

   <h2> Binding Styles</h2>
   <p v-bind:style="{
    color:colour,
    'font-size':fontSize+'px'}">1. Styles inline </p>
    
    <h4 v-bind:style="styles"> 2. Styles from object in data property</h4> 

    <hr><h1>Conditional Rendering</h1>
    <h2 v-if="num==0"> the number is zero</h2>
    <h2 v-else-if="num<0"> the number is negative</h2>
    <h2 v-else-if="num>0"> the number is positive</h2>
    <h2 v-else> not a number </h2>

    <hr><h1> List Rendering </h1>
    <h3  >1. Array of strings rendering</h3>
    <h3 v-for=" (name,index) in names" :key="name"> {{index}}{{name}} </h3>

    
    <h2>2. Array of objects rendering </h2>
    <div v-for="edu in education" :key=" edu.school">
      <h3> {{edu.school}}{{edu.percent}}</h3>
      
    </div>

    <h2>3. Array of array rendering </h2>
    <div v-for="fam in family" :key="fam.names">
      <h3> {{fam.names}}</h3>
      <h3 v-for="w in fam.whereabouts" :key="w"> {{w}}</h3>
    </div>

    <h2> 4. Objects rendering </h2>
    <h3 v-for="place in karur" :key="place">{{place}}</h3>
    
    
    <hr><h1> Conditional list rendering </h1>
     <template v-for="f in familymine" >
      <h1 v-if="name==='Rajendran'" :key="f.names">{{f}}</h1>
    </template>

    <hr>
    <h1> Methods </h1>
    <h3> no parameters {{ add()}}</h3>
    <h3>passing of parameters   {{ add1(5,6)}}</h3>
    <h3>one value is passed and other via this "(data())"{{ mult(6)}}</h3>
    <h3>one var defined in data property is passed and other via this {{ mult1(value)}}</h3>

   <hr>
   <h1> Event handlers </h1>
   <h4> {{name}}</h4>
   <button v-on:click = " name ='prabha'  "> click me</button>

   <h4> {{name1}}</h4>
   <button v-on:click = change()  > click me</button>
   <hr>

<h1> Form Handling </h1>
<form @submit="submitfn()">

<label for="name"> NAME </label>
<input type="text" id="name"  v-model="formvalues.formname"> 

<br><label for="gender"> Gender </label>
<br><input type="radio"   value=" male " v-model="formvalues.gender" > MAle 
<br><input type="radio"   value=" feale "  v-model="formvalues.gender"> feMAle    

<br><label for=" qualification">Select your qualification </label>
<br><select id=" qualification" multiple v-model="formvalues.qualification">    
<option value=" 10th"> 10th</option>
<option value=" 12th"> 12th</option>
<option value=" ug"> UG</option>
<option value=" pg"> PG</option>
</select>

<br><input type="checkbox" id=" submit" >
<label for ="submit"> i agree</label>

<br><button > Submit form </button>
</form>
<hr>
<h1> computed properties</h1>
<h3> {{fullfam }}</h3>
<button @click="family.push({names :' rajendran',whereabouts:[' ','working','karur']  })"> add another name</button>

<hr>
 <h1>Conditional list rendering using computed properties </h1>
  <h2 v-for="obj in full" :key="obj.name"> {{ obj.name}} {{obj.age}}</h2>

<hr> <h1> computed setters</h1>
<button @click="newEntry()"> Add new entry to Newobj </button>

<hr> <h1>Watchers </h1>
<h3> volume tracker </h3>
<h3> volume {{volume}} </h3>
<button @click=" volume = volume+2"> increase volume </button> 
<button @click=" volume -=1"> decrease volume </button>

<br> <br><input type="text" v-model="movie"> 

<br> <br><input type="text" v-model="me.name"> 
<br> <br><input type="text" v-model="me.age"> 

<br>
<br><button @click='moviearr.push( "  Sherlock  " )' > Add movie  </button>
<!--<button @click='moviearr=moviearr.concat( ["  Sherlock  " ])' > Add movie  </button>-->

<hr>
<br><h1> Components</h1>
<RamaPrabha name =" Rama " place =" karur"/>
<RamaPrabha name = "vaish" place="somewhere in KA "/>
<RamaPrabha :name = " course1" :place="course2 "/>
<br>

<br>
<h2> From NewCom component </h2>
<new-com id=" id class " movie="Enthiran"  :budget="200" :Status="true" > </new-com>
   </div>   
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import RamaPrabha from './components/RamaPrabha.vue'
import NewCom from './components/NewCom.vue'
export default {
  name: 'App',
  components:{
             // eslint-disable-next-line vue/no-unused-components
             RamaPrabha,NewCom
  },
  data(){   return{ 
 course1:" web development",
 course2:" cloud tech",

   name: " Rama" ,
   name1:"rama",
   lastname:"prabha",
   directive:" Directive v- text is implemented here...which can only be used for full text content",
   bindingHtml: '<u> Binding HTML Here  </u> ',
   placeholderforID:'realIdName',
   enabled:false,
   buttonHolderVue:'ButtonClassVue',
 colour: 'orange',
   fontSize:'30',
   styles:{
    color:'green',
    'font-size': '40px'
   },
   num: '0',
   names:['ramaprabha','21','karur'],
   education:[
    {
       school:"star",percent:"10th"},
       { school:"star hr sec",percent:"12th"}
    
   ],
   family:[
        {  names:"dhivya ",whereabouts:["2nd","studying", "chennai"]   },
        {  names :"rama",whereabouts:["1 st","working","karur"]  },   ],

   karur:{
    temp:"38 c",
    constituency:"4",
    day:"sept 30th"},
    
    familymine:{
      names:["Rajendran","Gunavathi","Ramaprabha","Dhivya"]
    },
    multiargs:"5",
    value:"4",

    formvalues:{
         formname:"",
         gender:"",
        qualification:[],
        ug:"",
    },
     
     newobj:[
      {name:"rajendran",
      age:"59"},
      {name:"gunavathi",
      age:"43"},
      {
        name:"Dhivya",
        age:"18"
      },
      {
        name:"rama",
        age:"21"
      }
     ],

     volume:0,
     movie:"movie",
     me:{
      name:"name",
      age:"age",
    
     }, 
     moviearr:[ " No way home"," far from home"]
     }
   
     },
    methods:{          
add(){
return 5+2;
},
add1(a,b){
return a+b;
},
mult(num){
  return num*this.multiargs;
},
mult1(num){
  return num*this.multiargs;
},
change(){
  return this.name1="last name prabha";
},
submitfn(Event){
  Event.preventDefault();
  console.log( " form submitted " + this.formvalues)},
  newEntry(){
    this.full="R "
  }  
  },
  
   
    computed:  {
 fullfam(){
  return this.family.reduce((all,curr)=> (all=all+curr.names ),""); 
},
filterfam(){
  return this.newobj.filter(item => item.age>50)
},
full:{
  get(){
  return this.newobj.filter(item => item.age>50)
  },
  set(value){
     this. lastname=value;
     console.log(this.lastname)
  }

}
    },
    watch:{
   volume(valuenew,valueold){

    if(valuenew>valueold && valuenew==6){
      
      return alert("Listening to higher volume will damage your ears")
    }

   },
   movie:{
    handler(val){
console.log(`calling api  ${val} `)
},
immediate:true,

   },
   me:{
    handler(Val){
      console.log(`loggin with deep name ${Val.name} and age ${Val.age}`  )
    },deep:true, immediate:true,
   },
   moviearr:{
    handler(Val){
      console.log(`adding new movie ${Val}`  )
      console.log(this.moviearr)
    },
    deep:true, 
    immediate:true,
   }
   
   
    }
  };

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.trueClass{
  color: orangered;
}
.trueClass2{
  font-size: 50px ;
}
.falseClass{
color:red;
}
.falseClass2{
  font-style: italic;
}
</style>
