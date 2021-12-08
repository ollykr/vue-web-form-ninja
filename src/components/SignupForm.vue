<template>
<!-- Two-way binding meaning : 1) we can use component's methods property to update a form field's value
2) and we can use form field's value to update components data property
v-model directive binds data in both directions
 -->
  <form>
      <label>Email:</label>
      <!-- use v-model="email" to bind the input with data's email value down below in data() -->
      <input type="email" required v-model="email">
      <label>Password:</label>
      <!-- use v-model="email" to bind the input with data's email value down below in data() -->
      <input type="password" required v-model="password">

      <label>Role: </label>
      <select v-model="role">
          <option value="developer">Web Developer</option>
          <option value="designer">Web Designer</option>
      </select>
  </form>
  <p>Email: {{ email }}</p>
  <p>Password: {{ password }}</p>
  <p>Role: {{ role }}</p>
</template>

<script>
export default {
data() {
    return {
        // email value gets updated from <input>'s text field
        // email property can be called anything else
        // values from form fields are assigned here
        email: '',
        password: '',
        // designer option is selected by default
        // if empty , no option displayed by default
        role: 'designer'
    }
}
}
</script>

<style>
form {
    max-width: 420px;
    margin: 30px auto;
    background: white;
    text-align: left;
    padding: 40px;
    border-radius: 10px;
  }
  label {
    color: #aaa;
    display: inline-block;
    margin: 25px 0 15px;
    font-size: 0.6em;
    text-transform: uppercase;
    letter-spacing: 1px;
    font-weight: bold;
  }
  input, select {
    display: block;
    padding: 10px 6px;
    width: 100%;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid #ddd;
    color: #555;
  }
</style>