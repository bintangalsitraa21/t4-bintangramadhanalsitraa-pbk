<template>
  <div class="fancy-btn">
    Tugas4 PBK
  </div>
  <div id="wrapper">
    <h1>Makanan</h1>
    <div class="card" v-for="x in Makanan" :key="x.name">
      <Makanan
        :Makanan-name="x.name"
        :Makanan-desc="x.desc"
        :is-favorite="x.favorite" 
        @toggle-favorite="receiveEmit" />
    </div>
    <br>
    <h1>Minuman</h1>
    <div class="card" v-for="x in Minuman" :key="x.name">
      <Minuman
        :Minuman-name="x.name"
        :Minuman-desc="x.desc"
        :is-favorite="x.favorite" 
        @toggle-favorite="receiveEmit" />
    </div>
    <br>
    <h1>Snack</h1>
    <div class="card" v-for="x in Snack" :key="x.name">
      <Snack
        :Snack-name="x.name"
        :Snack-desc="x.desc"
        :is-favorite="x.favorite" 
        @toggle-favorite="receiveEmit" />
    </div>
  </div>
</template>

<script>
import Makanan from './components/Makanan.vue';
import Minuman from './components/Minuman.vue';
import Snack from './components/Snack.vue';

export default {
  components: {
    Makanan,
    Minuman,
    Snack
  },
  data() {
    return {
      Makanan: [
        { name: 'Kimchi', desc: 'Fermented vegetables, typically cabbage, with chili pepper and seasoning', favorite: true },
        { name: 'Bibimbap', desc: 'Mixed rice with vegetables, beef, and a fried egg', favorite: false },
        { name: 'Bulgogi', desc: 'Grilled marinated beef', favorite: true },
        { name: 'Tteokbokki', desc: 'Stir-fried rice cakes in a spicy sauce', favorite: true }
      ],
      Minuman: [
        { name: 'Soju', desc: 'A clear, slightly sweet distilled beverage', favorite: true },
        { name: 'Makgeolli', desc: 'A milky, lightly sparkling rice wine', favorite: false },
        { name: 'Sikhye', desc: 'Sweet rice drink', favorite: true },
        { name: 'Bori-cha', desc: 'Roasted barley tea', favorite: true }
      ],
      Snack: [
        { name: 'Gim', desc: 'Dried seaweed sheets', favorite: true },
        { name: 'Tteok', desc: 'Korean rice cakes', favorite: false },
        { name: 'Hotteok', desc: 'Sweet pancakes filled with brown sugar, honey, nuts, and cinnamon', favorite: true },
        { name: 'Yanggaeng', desc: 'Sweet red bean jelly', favorite: true }
      ],
    };
  },
  methods: {
    receiveEmit() {
      alert('Telah ditambahkan ke favorite!');
    }
  }
};
</script>

<style>
  .fancy-btn {
    display: flex;
    justify-content: center;
    align-items: center;
    margin: 20px;
    padding: 10px;
    background-color: #ffaa64;
    border: 2px solid #f35454;
    border-radius: 10px;
    font-size: 1.2em;
    font-weight: bold;
    color: white;
    cursor: pointer;
  }
  
  #wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
  }

  h1 {
    color: #333;
    text-align: center;
    margin-bottom: 20px;
  }

  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 300px;
    padding: 20px;
    border: 1px solid #ddd;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    background-color: white;
    transition: transform 0.2s;
  }

  .card:hover {
    transform: scale(1.05);
  }

  .card h2 {
    margin: 10px 0;
    font-size: 1.5em;
    color: #f35454;
  }

  .card p {
    color: #666;
  }

  .card button {
    margin-top: 10px;
    padding: 10px 20px;
    background-color: #ffaa64;
    border: none;
    border-radius: 5px;
    color: white;
    font-size: 1em;
    cursor: pointer;
    transition: background-color 0.2s;
  }

  .card button:hover {
    background-color: #f35454;
  }
</style>
