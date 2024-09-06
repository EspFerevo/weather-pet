<!-- JS -->
<script>
import { IoRainyOutline } from 'oh-vue-icons/icons/io';

  export default {
    components: { 
        IoRainyOutline
    },

    data() {
      return {
        city: '',
      }
    },
  }
</script>

<!-- HTML CODE -->
<template>
  <div class="wrapper">
    <h1>Weather <IoRainyOutline /></h1>
    <p>Дізнайся погоду в {{ city == "" ? "твоєму місті" : city}}</p>
    <input type="text" v-model="city" placeholder="Введіть Ваше місто" />
    <button v-if="city !='' ">Отримати погоду</button>
    <button disabled v-else>Введіть назву міста</button>

  </div>
</template>

<!-- STYLES -->
<style scoped>
  .wrapper {
    width: 900px;
    height: 500px;
    border-radius: 50px;
    background: linear-gradient(135deg, #008080, #1e3c72);
    padding: 20px;
    text-align: center;
    color: white;
    box-shadow: 0px 10px 30px rgba(0, 0, 0, 0.3);
    position: relative;
    overflow: hidden;
  }

  .wrapper::before {
    content: '';
    position: absolute;
    top: -50%;
    left: -50%;
    width: 200%;
    height: 200%;
    background: radial-gradient(circle, rgba(255, 255, 255, 0.2), transparent);
    animation: rotate 6s linear infinite;
    z-index: 0;
  }

  @keyframes rotate {
    100% {
      transform: rotate(360deg);
    }
  }

  .wrapper h1 {
    margin-top: 50px;
    z-index: 1;
    position: relative;
    font-size: 2.5rem;
    text-transform: uppercase;
    letter-spacing: 3px;
    animation: glow 1.5s infinite alternate;
  }

  @keyframes glow {
    from {
      text-shadow:
        0 0 10px white,
        0 0 20px teal,
        0 0 30px cyan,
        0 0 40px cyan;
    }
    to {
      text-shadow:
        0 0 20px white,
        0 0 30px teal,
        0 0 40px cyan,
        0 0 50px cyan;
    }
  }

  .wrapper input {
    margin-top: 30px;
    background: transparent;
    border: 0;
    border-bottom: 2px solid white;
    font-size: 16px;
    padding: 8px 10px;
    outline: none;
    color: white;
    transition: border-bottom-color 0.3s ease;
    position: relative;
  }

  .wrapper input:focus {
    border-bottom-color: #ffa07a;
    box-shadow:
      0 0 10px #ffa07a,
      0 0 20px #ff7f50,
      0 0 30px #ff6347;
  }

  .wrapper button {
    background: transparent;
    color: white;
    border-radius: 20px;
    border: 2px solid #ffa07a;
    padding: 12px 20px;
    margin-left: 20px;
    cursor: pointer;
    position: relative;
    z-index: 1;
    transition:
      transform 0.4s ease,
      box-shadow 0.4s ease;
    font-size: 16px;
  }

  .wrapper button:hover {
    transform: scale(1.1) translateY(-5px);
    box-shadow:
      0 0 10px #ffa07a,
      0 0 20px #ff7f50,
      0 0 30px #ff6347;
  }

  .wrapper button:disabled { 
    background-color: rgb(22, 47, 55);
    cursor: not-allowed;
  }

</style>
