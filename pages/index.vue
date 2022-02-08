<template>
<div class="min-h-screen bg-gradient-to-r from-violet-500 to-fuchsia-500">


<div class="container mx-auto py-1 px-96">
<p class="text-white px-60 rounded-full border-4 text-2xl bg-blue-800">Create Customers</p>
</div>


<div class="container mx-auto py-8" >

  <!-- <button @click="goToPortal(1)">Click </button>  -->

<nuxt-link :to="{name:'portal-page1', params: { userId: 878866 }}" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-9 border border-blue-700 rounded" >Users</nuxt-link>

      <form :v-model="registro" class="py-4" ref="newEntryDetailForm">
        <div class="shadow overflow-hidden sm:rounded-md border-2 border-gray-800">
          <div class="px-4 py-5 bg-white sm:p-6">
            <div class="grid grid-cols-6 gap-6">
              <div class="col-span-6 sm:col-span-3">
                <label for="first-name" class="block text-sm font-medium text-gray-700">First name</label>
                <input type="text" name="first-name" v-model="registro.nombre" id="first-name" autocomplete="given-name" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-x-zinc-400 border-2 rounded-md py-3">
              </div>

              <div class="col-span-6 sm:col-span-3">
                <label for="last-name" class="block text-sm font-medium text-gray-700">Last name</label>
                <input  type="text" v-model="registro.apellido" name="last-name" id="last-name" autocomplete="family-name" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-x-zinc-400 border-2 rounded-md py-3">
              </div>

<!--               <ValidationProvider name="nombre" rules="required|nombre" v-slot="{ errors }">
  <input  type="text">
  <span>{{ errors[0] }}</span>
</ValidationProvider> -->

              <div class="col-span-6 sm:col-span-3">
                <label for="email-address" class="block text-sm font-medium text-gray-700">Email address</label>
                <input type="text" name="email-address" v-model="registro.correo" id="email-address" autocomplete="email" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-x-zinc-400 border-2 rounded-md py-3">
              </div>

              <div class="col-span-6 sm:col-span-3">
                <label for="country" class="block text-sm font-medium text-gray-700">Country</label>
                <select id="country" name="country" autocomplete="country-name" v-model="registro.pais" class="mt-1 block w-full py-3 px-3 border border-gray-300 bg-white rounded-md shadow-sm focus:outline-none focus:ring-indigo-500 focus:border-indigo-500 sm:text-sm">
  
                  <option value="United States">United States</option>
                  <option value="Canada">Canada</option>
                  <option value="Mexico">Mexico</option>
                </select>
              </div>

              <div class="col-span-6">
                <label for="street-address" class="block text-sm font-medium text-gray-700">Street address</label>
                <input type="text" name="street-address" id="street-address" v-model="registro.direccion" autocomplete="street-address" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-x-zinc-400 border-2 py-2 rounded-md">
              </div>

              <div class="col-span-6 sm:col-span-6 lg:col-span-2">
                <label for="city" class="block text-sm font-medium text-gray-700">City</label>
                <input type="text" name="city" id="city" autocomplete="address-level2" v-model="registro.ciudad" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-x-zinc-400 border-2 py-2 rounded-md">
              </div>

              <div class="col-span-6 sm:col-span-3 lg:col-span-2">
                <label for="region" class="block text-sm font-medium text-gray-700">State / Province</label>
                <input type="text" name="region" id="region" autocomplete="address-level1" v-model="registro.estado" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-x-zinc-400 border-2 py-2 rounded-md">
              </div>

              <div class="col-span-6 sm:col-span-3 lg:col-span-2">
                <label for="postal-code" class="block text-sm font-medium text-gray-700">ZIP / Postal code</label>
                <input type="text" name="postal-code" id="postal-code" autocomplete="postal-code" v-model="registro.zipcode" class="mt-1 focus:ring-indigo-500 focus:border-indigo-500 block w-full shadow-sm sm:text-sm border-x-zinc-400 border-2 py-2 rounded-md">
              </div>
            </div>
          </div>
          <div class="px-4 py-3 bg-gray-50 text-right sm:px-6">
            <button  type="button" @click="addItem('newEntryDetailForm',registro)" class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-indigo-600 hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
              Save
            </button>
          </div>
        </div>
      </form>
    </div>


 <div class="container mx-auto py-8">
        <table class="min-w-full divide-y divide-gray-200 border-2 border-gray-800">
          <thead class="bg-gray-50" >
            <tr>
              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                First Name
              </th>
              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                Last Name
              </th>
              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                Email
              </th>
              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                Country
              </th>

              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                Address
              </th>

              <th scope="col" class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
                City
              </th>
              
            </tr>
          </thead>
          <tbody class="bg-white divide-y divide-gray-200">
            <tr v-for="(item,i) in rowData" :key="i">
              <td>{{item.nombre}}</td>
              <td>{{item.apellido}}</td>
              <td>{{item.correo}}</td>
              <td>{{item.pais}}</td>
              <td>{{item.direccion}}</td>
              <td>{{item.ciudad}}</td>
    
            </tr>

          </tbody>
        </table>
      </div>

<!-- Alert message -->
<div class="container mx-auto py-8" >
  <div v-if="alertOpen" class="text-white px-6 py-4 border-0 rounded relative mb-4 bg-red-500">
    <span class="text-xl inline-block mr-5 align-middle">
      <i class="fas fa-bell"></i>
    </span>
    <span class="inline-block align-middle mr-8">
      <b class="capitalize">Ingresa todos los campos correspondientes!</b>
    </span>
    <button class="absolute bg-transparent text-2xl font-semibold leading-none right-0 top-0 mt-4 mr-6 outline-none focus:outline-none" v-on:click="closeAlert()">
      <span>×</span>
    </button>
  </div>
</div>

</div>



</template>

<script>

import {extend} from 'vee-validate';


export default {
  name: 'IndexPage',

  data(){
    return{
      rowData:[],
      alertOpen: false,
      registro:{
        nombre:'',
        apellido:'',
        correo:'',
        pais:'',
        ciudad:'',
        estado:'',
        direccion:'',
        zipcode:'',
      
      }
    }
  },

methods:{
  goToPortal(id){
    //this.$router.push('/portal/page1');
    this.$router.push({ name: '/portal/page1/', params: { id: 1 } })
  },

  addItem(formName, registro){

    if(this.registro.nombre == "" || this.registro.apellido == "" || this.registro.pais == "" || this.registro.direccion == ""){
      this.alertOpen = true;
    }


    else {

     console.log(formName);
     console.log(registro);
     this.rowData.push({nombre: registro.nombre, apellido: registro.apellido, correo: registro.correo, pais: registro.pais, ciudad: registro.pais, estado: registro.estado, direccion: registro.direccion, zipcode: registro.zipcode});

     this.registro.nombre = "";
     this.registro.apellido = "";
     this.registro.correo = "";
     this.registro.pais = "";
     this.registro.ciudad = "";
     this.registro.estado = "";
     this.registro.direccion = ""; 
     this.registro.zipcode = "";

     this.alertOpen = false;

    }

/*     this.$refs["formName"].validate(async (valid)=> {
      if(!valid){
        return false;
      }

    })  */  

  },

  closeAlert: function(){
      this.alertOpen = false;
    }
  }



}


</script>
