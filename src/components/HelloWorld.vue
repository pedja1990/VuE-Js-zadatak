<template>
  <div >

    <h1>Animals</h1>

    <form >
    
      <div>
        <label for="species">Species:</label>
        <input name = 'species' type="text" v-model = "addAnimal.species" >
      </div>
      <div>
        <label for="name">Name:</label>
        <input name = 'name' type="text"  v-model = "addAnimal.name">
      </div>
      <div>
        <label for="dateOfBirth">Date of birth:</label>
        <input name = 'dateOfBirth' type="text" v-model = "addAnimal.dateOfBirth" >
      </div>
      <button>Add Animal</button> // nece da se ubaci novi element u niz ?
      
    </form>

   <table >
     
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
           <td >
            <button  @click="remove(index)">Remove</button>
            <button  @click="moveToTop(animal)">Move to top</button>
          </td>
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
          name: 'Jack',
          dateOfBirth: '12-12-2021',
          
        },
        {
          species: 'Cat',
          name: 'Tom',
          dateOfBirth: '05-05-2021',
          
        },
        {
          species: 'Fish',
          name: 'Nemo',
          dateOfBirth: '',
         
        },

        {
          species: 'Tiger',
          name: 'SherKahn',
          dateOfBirth: '',
         
        },
        {
          species: 'Lion',
          name: 'Simba',
          dateOfBirth: '',
         
        }
      ],
    };
  },
  methods: {
    remove(index) {
      const animal = this.animals.indexOf(index);
      this.animals.splice(animal, 1);
    },
    moveToTop(animal) {
      this.remove(animal);
      this.animals.unshift(animal);
    },



    addAnimal() {
      this.animals.push(this.newAnimal);
      this.newAnimal = {
        species: '',
        name:'',
        dateOfBirth: null 
      };
    },

  }
};
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
