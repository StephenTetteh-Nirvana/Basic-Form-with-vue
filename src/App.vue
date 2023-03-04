<template>
  <div>
    <pre>
    {{ JSON.stringify(formvalues,null,2) }}
    </pre>
  </div>
   <form @submit="formSubmit">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formvalues.name">
    </div>

     <div>
      <label for="age">Age</label>
      <input type="number" id="age" v-model.number="formvalues.age">
    </div>

    <div>
      <label for="profile">Profile Summary</label>
      <textarea  id=profile v-model="formvalues.profileSummary"></textarea>
    </div>
    <div>
      <label for="country">Select Your Country</label>
      <select id="country" v-model="formvalues.country">
        <option value="ghana">Ghana</option>
        <option value="india">India</option>
        <option value="nigeria">Nigeria</option>
      </select>
    </div>

    <div>
       <label for="jobLocation">Job Location</label>
     <select id="jobLocation" multiple v-model="formvalues.jobLocation">
        <option value="mongolia">Mongolia</option>
        <option value="china">China</option>
        <option value="Vietnam">Vietnam</option>
      </select>
    </div>

    <div>
      <input type="checkbox" id="checkbox" v-model="formvalues.remoteWork" true-value="yes" false-value="no"/>
      <label for="checkbox">Available For remote work</label>
    </div>

    <div>
      <input type="checkbox" id="html" v-model="formvalues.skills" value="html"/>
      <label for="html">HTML</label>
      <input type="checkbox" id="css" v-model="formvalues.skills" value="css"/>
      <label for="css">CSS</label>
      <input type="checkbox" id="javascript" v-model="formvalues.skills" value="javascript"/>
      <label for="javascript">JAVASCRIPT</label>
      <input type="checkbox" id="vue" v-model="formvalues.skills" value="vue"/>
      <label for="vue">VUE</label>
    </div>

    <div>
      <label>Years Of Experience</label>
      <input type="radio" id="0-2" value="0.2" v-model="formvalues.yearsofExperience"/>
      <label for="0-2">0-2</label>

      <input type="radio" id="3-5" value="3-5" v-model="formvalues.yearsofExperience"/>
      <label for="3-5">3-5</label>

      <input type="radio" id="5-10" value="5-10" v-model="formvalues.yearsofExperience"/>
      <label for="5-10">5-10</label>

      <input @keyup.enter=formSubmit type="radio" id="10+" value="10+" v-model="formvalues.yearsofExperience"/>
      <label for="10+">10+</label>
     </div>

     <button>Submit</button>
   </form>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      formvalues:{
        name:'',
        profileSummary:'',
        country:'',
        jobLocation: [],
        remoteWork:"no",
        skills:[],
        yearsofExperience:'',
        age: null
      }
    }
  },
   methods:{
       formSubmit(event){
          event.preventDefault()
          console.log(this.formvalues)
          alert('Your Job Application Form has been submitted successfully')
       }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
label{
  font-weight: bold;
  display:flex;
  margin-bottom:5px;
}
input + label{
 font-weight: bold;
 display: inline-flex;
 margin-right: 20px;
}

input[type='text'],
textarea,
select{
 display: block;
 width: 400px;
 padding: 6px 12px;
 font-size: 14px;
 line-height: 1.42;
 color:#555;
 background-color:#fff;
 background-image:none;
 border:1px solid #ccc;
 border-radius:4px;
}
</style>
