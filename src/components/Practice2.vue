<template lang="">
  <fieldset>
      <legend>Practice 2</legend>
      <form>
    <div class="form-group">
        <label for="name">Name</label>
        <input type="text" name="name" v-model="name"/>
        <p class="text-danger" v-if="!isNameValid">{{validNameMessage}}</p>
    </div>
    <div>
        <label for="age">Age</label>
        <input type="text" name="age" v-model="age"/>
        <p class="text-danger" v-if="!isAgeValid">{{validAgeMessage}}</p>
    </div>
    <div>
        <label for="address">Address</label>
        <input type="text" name="address" v-model="address"/>
        <p class="text-danger" v-if="!isAddressValid">{{validAddressMessage}}</p>
    </div>
    <button type="submit" @click.prevent="submitForm">Submit</button>
  </form>
  </fieldset>
</template>
<script>
export default {
    data() {
        return {
            name: '',
            age: '',
            address: '',
            isNameValid: true,
            validNameMessage: '',
            isAgeValid: true,
            validAgeMessage: '',
            isAddressValid: true,
            validAddressMessage: '',
        }
    },
    methods: {
        submitForm() {
            this.validName();
            this.validAge();
            this.validAddress();
            if (this.isNameValid && this.isAgeValid && this.isAddressValid) {
                alert(`Name: ${this.name} \n Age: ${this.age}\n Address: ${this.address}`)
            }
        },
        validName() {
            if (this.name.length == 0) {
                this.isNameValid = false;
                this.validNameMessage = 'Name is required'
            }
            else if (this.name.length > 50) {
                this.isNameValid = false;
                this.validNameMessage = 'Name must less than 50 characters'
            }
            else {
                this.isNameValid = true;
            }
        },
        validAge() {
            if (this.age.length == 0) {
                this.isAgeValid = false;
                this.validAgeMessage = 'Age is required'
            }
            else {
                var age = parseInt(this.age);
                if (age) {
                    if (age > 0) {
                        this.isAgeValid = true;
                    }
                    else {
                        this.isAgeValid = false;
                        this.validAgeMessage = 'Age must larger than 0'
                    }
                }
                else {
                    this.isAgeValid = false;
                    this.validAgeMessage = 'Age must a number'
                }

            }

        },
        validAddress() {
            if (this.address.length == 0) {
                this.isAddressValid = false;
                this.validAddressMessage = 'Address is required'
            }
            else {
                this.isAddressValid = true;
            }
        }
    },
};
</script>
<style scoped>
.text-danger {
    color: red;
}
</style>
