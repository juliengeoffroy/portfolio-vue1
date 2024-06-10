<script setup>
  import emailjs from "@emailjs/browser";
  import { ref } from "vue";
  const last_name = ref("");
  const first_name = ref("");
  const object = ref("");
  const message = ref("");
  const valueMissing = ref("");

  function sendEmail() {
    (function () {
      emailjs.init("en-GWbfN6-HqSTv3m");
    })();

  const params = {
    to_name: "JULIEN",
    from_name: last_name.value + "" + first_name.value,
    about: object.value,
    message: message.value,
    email: "djugeoffroy@gmail.com",
  };

  emailjs
    .send("service_msjzgvm", "template_6flcsrc", params)
    .then((res) => {
      alert("E-mail envoyé avec succès");
    })
    .catch();
  };

</script>

<template>
  <section id="contact">
    <h1 class="title">Contact</h1>
    <a class="text-2xl" style="color: black;">
      <ul>
        <li><a href="mailto:djugeoffroy@gmail.com">djugeoffroy@gmail.com</a></li>
      </ul> 
    </a>  
    <form @submit.prevent="sendEmail()">
      <div class="name">
        <div class="form_items name">
          <label for="lat_name">Nom:</label>
          <input
            type="text"
            v-model.trim="last_name"
            name="last_name" 
            id="last_name" 
            required
          />
        </div>
        <div class="form_items name">
          <label for="first_name">Prénom:</label>
          <input 
            type="text"
            vmodel.trim="first_name"
            name="first_name"
            id="first_name" 
            required
          />
        </div>
        <div class="form_items">
          <label for="object">Objet: </label>
          <input 
            type="text"
            v-model.trim="object"
            name="object"
            id="object" 
            required
          />
        </div>
        <div class="form_items">
          <label for="message" id="message_title">Message: </label>
          <textarea v-model.trim="message" name="message" id="message" required>
          </textarea>
        </div>
        <input type="submit" value="Envoyer" id="submit_button" />
      </div>
    </form>
  </section>
</template>
  
<style scoped>

  li{
    color: black;
  }

  a{
    color: black;
  }

  section:hover > h1 {
    text-decoration: underline solid;
  }
  
  form {
    display: flex;
    flex-direction: column;
    width: 60%;
    min-width: 600px;
    margin-bottom: 10px;
  }
  
  .name {
    display: flex;
    flex-direction: row;
    }
  
  .form_items {
    display: flex;
    font-size: 2em;
    padding: 5px;
    margin: 5px;
    align-items: center;
  }
  
  #submit_button {
    width: 150px;
    align-self: center;
  }
  
  input {
    margin-left: 10px;
    width: 150px;
    background-color: cadetblue;
    color: aliceblue;
  }
  
  label {
    margin-left: 45px;
  }
  
  #message_title {
    margin-left: 0px;
  }
  
  textarea {
    width: 250px;
    min-height: 100px;
    margin-left: 10px;
    background-color: cadetblue;
    color: aliceblue;
  }
  
  .error {
    background-color: red;
  }
</style>