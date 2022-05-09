<template>
    <fieldset>
        <legend>Practice 3</legend>
        <form>
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" name="name" v-model="name" />
            </div>
            <div>
                <label for="age">Age</label>
                <input type="text" name="age" v-model="age" />
            </div>
            <div>
                <label for="address">Address</label>
                <input type="text" name="address" v-model="address" />
            </div>
            <button type="submit" @click.prevent="filter">Submit</button>
        </form>
        <table>
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Age</th>
                    <th>Address</th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="employee in filterEmployee">
                    <td>{{employee.name}}</td>
                    <td>{{employee.age}}</td>
                    <td>{{employee.address}}</td>
                    <th>
                        <button @click="this.$emit('employee-detail',employee)">Detail</button>
                    </th>
                </tr>
            </tbody>
        </table>
    </fieldset>
</template>
<script>
export default {
    data() {
        return {
            name: '',
            age: '',
            address: '',
            employees: [
                {
                    name: 'John',
                    age: 20,
                    address: 'Pham hung'
                },
                {
                    name: 'Doe',
                    age: 30,
                    address: 'Tran duy hung'
                },
                {
                    name: 'Lorem',
                    age: 23,
                    address: 'Trung kinh'
                }
            ],
            filterEmployee:[]
        }
    },
    methods:{
        filter(){
            this.filterEmployee=this.employees.filter(item=>item.name.toLowerCase().includes(this.name.toLowerCase()) 
            && item.age.toString().includes(this.age) && item.address.toLowerCase().includes(this.address.toLowerCase()));
        }
    },
    mounted() {
        this.filterEmployee=this.employees;
    },
    // computed: {
    //     filterEmployee() {
    //         return this.employees.filter(item=>item.name.toLowerCase().includes(this.name.toLowerCase()) 
    //         && (item.age==this.age || this.age=='') && item.address.toLowerCase().includes(this.address.toLowerCase()));
    //     }
    // }
}
</script>
<style scoped>
table {
    border: 1px solid #ccc;
}

/* table t {
    border: 1px solid #ccc;
} */
</style>