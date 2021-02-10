<template>
  <section class='highlight content-section'>
    
  <div class="container">
    <div class="highlight-right">
    <div class="email">
    <label for="email" >Email</label>
    </div>
    <p>
    <input type="email" id="email" name="email" placeholder="email@email.com">
    </p>

    <div class="company">
    <label for="company">Company</label>
    </div>
    <p>
    <input type="text" id="company" name="company" placeholder="">
    </p>

    <div class="description">
    <label for="description">Description</label>
    </div>
    <p>
    <input type="text" id="description" name="description" placeholder="">
    </p>

    
    </div>
    <div class="highlight-left">
      <div class="name">
      <label for="name">Name</label>
      </div>
      <p>
      <input type="text" id="name" name="name" placeholder="Your name..">
      </p>
      
      
      <div class="message">
      <label for="Message">Message</label>
      </div>
      <p>
      <select id="message" name="message">
      <option value="Graduate">Graduate</option>
      <option value="Company">Company</option>
      <option value="Investor">Investor</option>
      <option value="Apprentice">Apprentice</option>
      <option value="Journalist">Journalist</option>
      </select>
      </p>
      <br>
      <br>
      <br>
      <br>
      

    </div>
    </div>
    
    <input type="submit" value="Submit">

    

  </section>
</template>

<script>
export default {
  props: ['slice'],
  name: 'contact-slice'
}
</script>

<style scoped>


.container {
  
        display: flex;
        align-items: center;
        justify-content: center;
        padding-top:50px;
        border-style: solid;
        border-width: 2px 2px 2px 2px;
        border-color: whitesmoke;
        
        
      }

.highlight-right {
  order: 5;
  padding-left: 200px;
  
}

input[type=text] {
  width: 300px;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type=submit] {
  width: 100%;
  background-color: purple;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;

}

input[type=submit]:hover {
  background-color: rgb(177, 7, 177);;
}

input[type=email]{
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  border:none;
  border-bottom: 2px dotted #555;
}

select {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  border:none;
  border-bottom: 2px dotted #555;
  
}

input:focus {
  border: 3px solid #555;
}

.email{
  border-radius: 15px;
  background: rgb(170, 222, 243);
  padding: 10px 15px 10px 15px;
  width: 50px;
  margin-left:120px;
}
.company{
  border-radius: 15px;
  background: skyblue;
  padding: 10px 15px 10px 15px;
  width: 100px;
  margin-left:100px;
}
.description{
  border-radius: 15px;
  background:rgb(192, 139, 192) ;
  padding: 10px 15px 10px 15px;
  width: 110px;
  margin-left:100px;
}
.name{
  border-radius: 15px;
  background:rgb(243, 208, 214);
  padding: 10px 15px 10px 15px;
  width: 50px;
  margin-left:100px;
}
.message{
  border-radius: 15px;
  background: rgb(243, 243, 91);
  padding: 10px 15px 10px 15px;
  width: 90px;
  margin-left:100px;
}

input[type=text] {
  border:none;
  border-bottom: 2px dotted #555;
}

::-webkit-input-placeholder {
   text-align: center;
}

</style>
