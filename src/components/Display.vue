<template>
  <div class="display">
    <input type="text" class="calculator-screen" value="0" disabled />

    <div class="calculator-keys">
      <button type="button" class="clear" value="clear">C</button>
      <button type="button" class="operator" value="(">(</button>
      <button type="button" class="operator" value=")">)</button>
      <button type="button" class="operator" value="/">&divide;</button>

      <button type="button" value="7">7</button>
      <button type="button" value="8">8</button>
      <button type="button" value="9">9</button>
      <button type="button" class="operator" value="*">&times;</button>

      <button type="button" value="4">4</button>
      <button type="button" value="5">5</button>
      <button type="button" value="6">6</button>
      <button type="button" class="operator" value="-">-</button>

      <button type="button" value="1">1</button>
      <button type="button" value="2">2</button>
      <button type="button" value="3">3</button>
      <button type="button" class="operator" value="+">+</button>

      <button type="button" value="00">00</button>
      <button type="button" value="0">0</button>
      <button type="button" class="decimal" value=".">.</button>
      <button type="button" class="equal-sign" value="=">=</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "display",
};
</script>

<style scoped>
.display {
  /* background-color: #0f0f0f; */
  background-color: white;
  width: 350px;
  height: 700px;
  margin: 0 auto;
  border-radius: 4rem;
  padding: 3rem;
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.20), 0 2px 20px rgba(0, 0, 0, 0.20),
    0 4px 40px rgba(0, 0, 0, 0.20), 0 8px 8px rgba(0, 0, 0, 0.20),
    0 16px 20px rgba(0, 0, 0, 0.20);
}

input {
  background-color:#000;
  border: 1px solid #000;
  position: relative;
  left: 28%;
  top: 10%;
  width: 40%;
  height: 20%;
  text-align: right;
  margin-bottom: 5rem;
}
.calculator-keys {
  display: grid;
   grid-template-columns: repeat(4, 1fr);
  grid-row-gap: 20px;
  grid-column-gap: 20px;
  margin-top: 3rem;
 

}

button {
  height: 60px;
  background-color: #000;
  border: 1px solid #000;
  border-radius: 50%;
  font-size: 2rem;
  color: #fff;
  box-shadow: 0px 17px 10px -10px rgba(0,0,0,1);
  cursor: pointer;
  transition: all ease-in-out 300ms;
  outline: none;
  
}
 

button:hover {
   box-shadow: 0px 37px 20px -20px rgba(0,0,0,0.2);
    transform: translate(0px, -10px) scale(1.2);
    padding: 10px;
}

.operator {
  color: #f0595f;
}

.clear {

  color:#f0595f;
}

.equal-sign {
  
  color: #f0595f;
}







</style>
