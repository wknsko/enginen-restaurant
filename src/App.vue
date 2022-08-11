<template>

  <header>
    <div class="restaurant">
      Enginen Restaurant
    </div>
    <div class="text" v-for="(item, i) in headers" :key="i">
      <transition name="fade">
        <div class="slide" v-if="currentIdx === i">
          <div class="title">{{headers[currentIdx].title}}</div>
          <div class="text">{{ item.text }}</div>
          <button class="btn-header">{{ item.btnText }}</button>
        </div>
      </transition>
    </div>
  </header>

  <div class="info">

    <div class="row-one">
      <h2> Enjoy modern Italian cuisine at the highest level.</h2>
      <div class="line"></div>
      <div class="text">Cras mattis iudicium purus sit amet fermentum at nos hinc posthac, sitientis piros afros. Lorem
        ipsum dolor sit amet, consectetur adipisici elit, petierunt uti sibi.</div>
      <img src="./assets/food-2.jpeg" alt="">
    </div>

    <div class="row-tw">
      <img src="./assets/food-3.jpeg" alt="">
      <h2>Authentic fresh food in a really nice quaint environment.</h2>
      <div class="line"></div>
      <div class="text">
        Authentic fresh food in a really nice quaint environment.
        Cras mattis iudicium purus sit amet fermentum at nos hinc posthac, sitientis piros afros. Lorem ipsum dolor sit
        amet, consectetur adipisici elit, petierunt uti sibi.</div>
    </div>
  </div>

  <div class="parralax">
    <div class="first">
      <h2>Experience classic Italian food using only fresh ingredients.</h2>
      <div class="line"></div>
      <div class="text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Corporis vel, ipsam repellendus Lorem
        ipsum dolor sit .</div>
    </div>
    <div class="icons">
      <div v-for="item in iconItems" :key="item">
        <img :src="item.url" alt="">
        <h4>{{item.title}}</h4>
        <div class="text">{{item.text}}</div>
      </div>
    </div>
  </div>

  <div class="menu-header">
    <h2>Our menu</h2>
    <div class="text">We are committed to satisfying our customers with great food and excellent service. We offer a
      wide variety of delicious Italian dishes.</div>
  </div>



  <div class="menu">

    <h3>Specialita della casa</h3>

    <div class="menu-item" v-for="(item, i) in menu.specials" :key="i">
      <h4>{{item.name}}</h4>
      <div class="description">{{item.description}}</div>
      <div class="price">{{item.price}}</div>
    </div>

    <h3>Pasta specials</h3>

    <div class="menu-item" v-for="(item, i) in menu.pasta" :key="i">
      <h4>{{item.name}}</h4>
      <div class="description">{{item.description}}</div>
      <div class="price">{{item.price}}</div>
    </div>

    <h3>Traditional Dishes</h3>

    <div class="menu-item" v-for="(item, i) in menu.traditional" :key="i">
      <h4>{{item.name}}</h4>
      <div class="description">{{item.description}}</div>
      <div class="price">{{item.price}}</div>
    </div>

  </div>



  <div class="booking">
    <div class="title">
      Booking a table online is easy and takes just a couple of minutes.
    </div>
    <div class="input-area">
      <input type="date">
      <input type="number" placeholder="people">
      <input type="text" placeholder="Name">
      <input type="text" placeholder="Phone">
    </div>
    <button class="btn-book">Find a table</button>
  </div>

  <div class="map">
    <iframe
      src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3302.0565234290866!2d-118.162695!3d34.144895999999996!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x80c2c39e84d01593%3A0xe20b9201b0cdab58!2s49%20S%20Grand%20Ave%2C%20Pasadena%2C%20CA%2091105%2C%20USA!5e0!3m2!1sen!2scz!4v1660164751892!5m2!1sen!2scz"
      width="100%" height="600" style="border:0; filter: grayscale()" allowfullscreen="" loading="lazy"
      referrerpolicy="no-referrer-when-downgrade"></iframe>
  </div>

  <div class="restaurant-info">

    <div class="details">
      <h3> Contact Details </h3>
      <img src="" alt=""> 49 Grand Street, Los Angeles <br />
      <img src="" alt="" /> (222) 400-630 <br />
      <img src="" alt="" /> contact@leadengine.com <br />
    </div>
    <div class="hours">
      <h3>Opening Hours</h3>
      <div class="row">
        <div class="days"> Monday-Friday</div>
        <div class="time">10:00 - 18:00</div>
      </div>
      <div class="row">
        <div class="days">Saturday</div>
        <div class="time">10:00 - 14:00</div>
      </div>
      <div class="row">
        <div class="days">Sunday</div>
        <div class="time">Closed</div>
      </div>
    </div>

  </div>



</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      headers: [
        { title: 'Reserve your culinary experience', text: `Experience classic Italian food using only fresh ingredients. Authentic fresh food in a really nice quaint environment.`, btnText: 'Show menu' },
        { title: 'Food that tastes great as it looks', text: `Experience classic Italian food using only fresh ingredients. Authentic fresh food in a really nice quaint environment.`, btnText: 'Reserve a table' }
      ],
      iconItems: [
        { url: require(`./assets/chef.png`), title: 'Italian Chef', text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet.'},
        { url: require(`./assets/contract.png`), title: 'Authentic recipes', text: 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Lorem ipsum dolor sit amet.' }
      ],
      menu:  {
        specials: [
          { name: 'Penne Palamino', description: 'Sapien nunc amet ultrices, ipsum velit purus aliquet, massa fringilla leo orci.', price: '$9.50'},
          { name: 'Linguini con Vongle', description: 'Vitae justo adipiscing elit ut fermentum. Velit egestas dui id ornare.', price: '$12.00' },
          { name: 'Egg Plant Parmigiana', description: 'Sapien nunc amet ultrices, ipsum velit purus aliquet, massa fringilla leo orci.', price: '$10.00' },
          { name: 'Tortellini Primavera', description: 'Vitae justo adipiscing elit ut fermentum. Velit egestas dui id ornare.', price: '$8.50' }
        ],
        pasta: [
          { name: 'Pasta al Forno with Sugo', description: 'Sapien nunc amet ultrices, ipsum velit purus aliquet, massa fringilla leo orci.', price: '$9.50' },
          { name: 'Zesty Spaghetti a la Puttanesca', description: 'Vitae justo adipiscing elit ut fermentum. Velit egestas dui id ornare.', price: '$12.00' },
          { name: 'Ricotta and Grana Padano Gnocchi', description: 'Sapien nunc amet ultrices, ipsum velit purus aliquet, massa fringilla leo orci.', price: '$10.00' },
          { name: 'Fettuccine con Carciofi', description: 'Vitae justo adipiscing elit ut fermentum. Velit egestas dui id ornare.', price: '$8.50' }
        ],
        traditional: [
          { name: 'Zuppa del Giorno', description: 'Sapien nunc amet ultrices, ipsum velit purus aliquet, massa fringilla leo orci.', price: '$8.00' },
          { name: 'Bruschette Pomodoro Aglio', description: 'Vitae justo adipiscing elit ut fermentum. Velit egestas dui id ornare.', price: '$11.50' },
          { name: 'Crostini con Tonno', description: 'Sapien nunc amet ultrices, ipsum velit purus aliquet, massa fringilla leo orci.', price: '$10.50' },
          { name: 'Antipasto di Verdure alla Griglia', description: 'Vitae justo adipiscing elit ut fermentum. Velit egestas dui id ornare.', price: '$12.00' }
        ]
      },
      currentIdx: 0
      
    }
  },
  methods: {
      setAutoRoll() {
        setInterval(() => {
          this.currentIdx === 0 ? this.currentIdx = 1 : this.currentIdx = 0;
          this.show = !this.show
        }, 8000)
      }
  },
  mounted() {
    this.setAutoRoll();
  },
  components: {
    
  }
}
</script>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: all 2s ease-in-out;
  overflow: hidden;
  
  opacity: 0;
  position: absolute;
}

.fade-enter,
.fade-leave-to {
  opacity: 0;
  visibility: hidden;
}

</style>
