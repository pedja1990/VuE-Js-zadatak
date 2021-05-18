<template>
  <div >

    <h1>Animals</h1>


    <table class="table">
      <thead>
        <tr>
          <th>Species</th>
          <th>Name</th>
          <th>Date of birth</th>
          
        </tr>
      </thead>
      <tbody>
        <tr v-for="(animal, key) in animals" :key="key">
          <td>{{ animal.species }}</td>
          <td>{{ animal.name }}</td>
          <td>{{ animal.dateOfBirth ? animal.dateOfBirth : 'Nepoznat' }}</td>
        </tr>
      </tbody>
    </table>
    
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  
 
  data() {
    return {
      
      animals: [
        {
          species: 'Dog',
          name: '',
          dateOfBirth: '17-05-2021',
       
        },
        {
          species: 'Cat',
          name: 'tom',
          dateOfBirth: '05-05-2021',
          
        },
        {
          species: 'Fish',
          name: 'fish',
          dateOfBirth: '',
          
        },
         {
          species: 'Tiger',
          name: 'SherKhan',
          dateOfBirth: '',
          
        },
          {
          species: 'Lion',
          name: 'Simba',
          dateOfBirth: '',
          
        },

      ],
    };
  }







}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
