<script>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Contact from './components/Contact.vue'
import Cardlist from './components/Cardlist.vue'
import FoodCard from './components/FoodCard.vue'
import Menupage from './components/Menupage.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Home,
    About,
    Contact,
    Cardlist,
    FoodCard,
    Menupage,
    Footer
  },

  data() {
    return {
      currentPage: 'Home',
      isCartOpen: false,
      cartItems: [],
      selectedCategory: 'All',
      categories: ['Meals', 'Snacks', 'Drinks', 'Dessert'],

      foods: [
        {
          id: 1, name: 'CHICKEN POTATO',
          price: 220,
          image: 'https://i.pinimg.com/736x/04/39/47/04394754d461573412134b960a6130fe.jpg',
          description: 'chicken potato a hearty, satisfying, and deeply savory profile.',
          category: 'Meals'
        },
        {
          id: 2,
          name: 'SALMON',
          price: 300,
          image: 'https://i.pinimg.com/736x/02/20/81/022081ead8a4632c56a3e2c04d942d64.jpg',
          description: 'it is a flaky pink fish with a rich, buttery flavor and crisp skin',
          category: 'Meals'
        },
        {
          id: 3,
          name: 'SHRIMP',
          price: 210,
          image: 'https://i.pinimg.com/1200x/65/de/59/65de59148c35150f2c64da8f36dbc5cd.jpg',
          description: 'a culinary seafood dish made with fresh or frozen shrimp.',
          category: 'Meals'
        },
        {
          id: 4,
          name: 'BEEF STEAK',
          price: 200,
          image: 'https://i.pinimg.com/1200x/b4/b5/96/b4b5961674d0103249a7ad249972c66c.jpg',
          description: 'featuring thinly sliced beef braised in soy sauce and citrus.',
          category: 'Meals'
        },
        {
          id: 5,
          name: 'LECHON BELLY',
          price: 250,
          image: 'https://i.pinimg.com/1200x/b3/30/5b/b3305b49db5af4ba7934c453b18afed0.jpg',
          description: 'classic flavors of whole-pig lechon on a smaller, convenient scale.',
          category: 'Meals'
        },
        {
          id: 6,
          name: 'CHICKEN BUFFALO',
          price: 200,
          image: 'https://i.pinimg.com/1200x/33/f8/f9/33f8f955b818f768e7a463f53a1cbea6.jpg',
          description: 'traditionally fried wings or baked/grilled chicken breasts.',
          category: 'Meals'
        },
        {
          id: 7,
          name: 'CHICKEN SKEWERS',
          price: 280,
          image: 'https://i.pinimg.com/736x/f8/90/5f/f8905fb9a92dcce4cad6a1de300c782f.jpg',
          description: 'marinated chicken breast or thigh threaded onto wooden or metal sticks.',
          category: 'Meals'
        },
        {
          id: 8,
          name: 'CARBONARA',
          price: 250,
          image: 'https://i.pinimg.com/736x/d5/13/84/d513842a5df920975b0354d8d2df06ea.jpg',
          description: 'glossy sauce of eggs, hard cheese, cured pork, and black pepper.',
          category: 'Meals'
        },
        {
          id: 9,
          name: 'CHURROS',
          price: 220,
          image: 'https://i.pinimg.com/1200x/23/cc/17/23cc176e7e967058152d2dcb51a5f7fc.jpg',
          description: 'ridged, deep-fried choux pastry sticks coated in cinnamon sugar.',
          category: 'Snacks'
        },
        {
          id: 10,
          name: 'MOZZARELLA STICKS',
          price: 300,
          image: 'https://i.pinimg.com/1200x/b7/96/d6/b796d636c0055dda3875ff0ba1bd2cef.jpg',
          description: 'deep-fried made from elongated pieces of mozzarella cheese.',
          category: 'Snacks'
        },
        {
          id: 11,
          name: 'BANANA SPLIT',
          price: 210,
          image: 'https://i.pinimg.com/236x/b1/5f/77/b15f77c5fb89bfc42f1c86c20466f605.jpg',
          description: 'a peeled banana in half lengthwise and placing it in a long dish.',
          category: 'Snacks'
        },
        {
          id: 12,
          name: 'GOURMET FRIES',
          price: 200,
          image: 'https://i.pinimg.com/736x/56/85/94/568594ff03c43418b3a3b913553e01d3.jpg',
          description: 'deep-fried strips of potato featuring a crispy exterior and a soft, fluffy interior.',
          category: 'Snacks'
        },
        {
          id: 13,
          name: 'MEATBALLS',
          price: 250,
          image: 'https://i.pinimg.com/736x/6a/7d/cd/6a7dcd1a64bf68b6b0ef12c552949978.jpg',
          description: 'a small, round sphere made from chopped or ground meat',
          category: 'Snacks'
        },
        {
          id: 14,
          name: 'BURGER WITH FRIES',
          price: 200,
          image: 'https://i.pinimg.com/1200x/58/5a/71/585a71fd86e109b465027a49c1cd84bd.jpg',
          description: 'a hearty, savory comfort meal pairing a warm, meat-filled sandwich.',
          category: 'Snacks'
        },
        {
          id: 15,
          name: 'BEEF NACHOS',
          price: 280,
          image: 'https://i.pinimg.com/1200x/0d/85/09/0d85096318a1fe35edf41121a775c503.jpg',
          description: 'crisp corn tortilla chips, layered or topped with savory beef and cheese.',
          category: 'Snacks'
        },
        {
          id: 16,
          name: 'CRUNCHY COOKIES',
          price: 250,
          image: 'https://i.pinimg.com/736x/8e/9d/b6/8e9db66afe221bf69e2dce0bb91aa15f.jpg',
          description: 'driven by a lower moisture content and specific ingredient ratios.',
          category: 'Snacks'
        },
        {
          id: 17,
          name: 'COCKTAILS',
          price: 220,
          image: 'https://i.pinimg.com/736x/bb/d2/ea/bbd2ea0272a9f108ada78b7b03f9257a.jpg',
          description: 'made by combining a distilled spirit with other ingredients.',
          category: 'Drinks'
        },
        {
          id: 18,
          name: 'FRUITY DRINKS',
          price: 300,
          image: 'https://i.pinimg.com/736x/68/59/e9/6859e9081fa489b6c312d82fe1a4588c.jpg',
          description: 'cooked fruit flavor profile rather than a single narrow spice.',
          category: 'Drinks'
        },
        {
          id: 19,
          name: 'ICED TEA LEMON',
          price: 210,
          image: 'https://i.pinimg.com/1200x/80/15/4c/80154c2c9b7008f13e1e821ccd680cb3.jpg',
          description: 'a cold, refreshing beverage made by combining chilled brewed tea',
          category: 'Drinks'
        },
        {
          id: 20,
          name: 'COCA COLA',
          price: 200,
          image: 'https://i.pinimg.com/736x/86/d8/9a/86d89aececbf4358d73d828be06bf5b5.jpg',
          description: 'a flavor profile built on a blend of caramel sweetness, citrus oils',
          category: 'Drinks'
        },
        {
          id: 21,
          name: 'LEMON JUICE',
          price: 250,
          image: 'https://i.pinimg.com/736x/b2/fd/29/b2fd29e9ba90752c1f60c120cb700348.jpg',
          description: 'the acidic, sour liquid obtained by squeezing the endocarp of lemons.',
          category: 'Drinks'
        },
        {
          id: 22,
          name: 'SPRITE',
          price: 200,
          image: 'https://i.pinimg.com/736x/fa/8d/7c/fa8d7c7b3c7fef50a044e2dcbb018a0d.jpg',
          description: 'This is a clear, caffeine-free, lemon-lime-flavored soft drink',
          category: 'Drinks'
        },
        {
          id: 23,
          name: 'BLUE LEMONADE',
          price: 280,
          image: 'https://i.pinimg.com/736x/b6/a5/16/b6a51678cec52d7fc060cbcf21361565.jpg',
          description: 'characterized by its bright blue color and refreshing lemon flavor.',
          category: 'Drinks'
        },
        {
          id: 24,
          name: 'ORANGE JUICE',
          price: 250,
          image: 'https://i.pinimg.com/736x/dd/e6/c1/dde6c19f17fa56e1fafaa35e020b0756.jpg',
          description: 'a liquid extract produced by squeezing or reaming the fruit of the orange tree',
          category: 'Drinks'
        },
        {
          id: 25,
          name: 'LECHE FLAN',
          price: 220,
          image: 'https://i.pinimg.com/736x/e8/50/08/e8500899188333b4f9868dbe561fa80f.jpg',
          description: 'a rich, dense, and sweet Filipino caramel custard dessert.',
          category: 'Dessert'
        },
        {
          id: 26,
          name: 'BELGIAN WAFFLE',
          price: 300,
          image: 'https://i.pinimg.com/736x/48/2a/57/482a5709b40093d1d5ffc035a5386f5e.jpg',
          description: 'leavened waffle featuring a light, airy interior, a crispy exterior',
          category: 'Dessert'
        },
        {
          id: 27,
          name: 'MANGO CREAM CREPES',
          price: 210,
          image: 'https://i.pinimg.com/736x/ff/af/7c/ffaf7ce0e5b1617ca8ee863b36b984a8.jpg',
          description: 'filled with sweet vanilla-scented whipped cream and fresh mango chunks.',
          category: 'Dessert'
        },
        {
          id: 28,
          name: 'JAPANESE PANCAKE',
          price: 200,
          image: 'https://i.pinimg.com/736x/a9/fe/75/a9fe75a4c0f2a123abac66dbb71085ec.jpg',
          description: 'lighter and airier than traditional Western pancakes.',
          category: 'Dessert'
        },
        {
          id: 29,
          name: 'BISCOFF CHEESECAKE',
          price: 250,
          image: 'https://i.pinimg.com/1200x/63/dc/b2/63dcb2aeda165413627206d7c389f345.jpg',
          description: 'spiced flavor of Lotus Biscoff cookies and cookie butter.',
          category: 'Dessert'
        },
        {
          id: 30,
          name: 'OREO MILKSHAKE',
          price: 200,
          image: 'https://i.pinimg.com/736x/db/4f/6f/db4f6fe576135014305f0547721362ff.jpg',
          description: 'made by blending milk, ice cream, and crushed Oreo cookies.',
          category: 'Dessert'
        },
        {
          id: 31,
          name: 'ICE CREAM',
          price: 280,
          image: 'https://i.pinimg.com/736x/8e/97/55/8e975567149d3288383e559f8c819668.jpg',
          description: 'made from a mixture of milk, cream, sugar, and flavorings',
          category: 'Dessert'
        },
        {
          id: 32,
          name: 'MANGO FLOAT',
          price: 250,
          image: 'https://i.pinimg.com/1200x/8b/96/9e/8b969e362ba0e79d37468e4fa40eee93.jpg',
          description: 'crisp graham crackers, sweetened whipped cream, and ripe mango slices.',
          category: 'Dessert'
        }
      ]
    }
  },

  computed: {
    filteredFoods() {
      if (this.selectedCategory === 'All') {
        return this.foods;
      }
      return this.foods.filter(food => food.category === this.selectedCategory);
    },
    // Computes total count of items in the cart
    cartCount() {
      return this.cartItems.reduce((total, item) => total + item.quantity, 0);
    }
  },

  methods: {
    section(p) {
      this.currentPage = p;
      if (p === 'Menu') {
        this.selectedCategory = 'All';
      }
      this.navScroll();
    },
    navScroll() {
      window.scrollTo({ top: 0, behavior: 'smooth' });
    },
    openCartModal() {
      this.isCartOpen = true;
    },
    closeModal() {
      this.isCartOpen = false;
    },
    filterCategory(cat) {
      this.selectedCategory = cat;
      this.currentPage = 'FoodCard';
    },

    // Cart Actions
    addToCart(food) {
      alert('Added to Cart');
      const existing = this.cartItems.find(item => item.id === food.id);
      if (existing) {
        existing.quantity += 1;
      } else {
        this.cartItems.push({ ...food, quantity: 1 });
      }
    },
    updateCartQuantity({ id, quantity }) {
      const item = this.cartItems.find(item => item.id === id);
      if (item) {
        item.quantity = quantity;
      }
    },
    removeFromCart(id) {
      this.cartItems = this.cartItems.filter(item => item.id !== id);
    },
    clearCart() {
      this.cartItems = [];
    },
    payCart() {
      alert('Order placed successfully!');
      this.cartItems = [];
      this.isCartOpen = false;
    }
  }
}
</script>

<template>
  <Navbar :cart-count="cartCount" @GoTo="section" @showCartModal="openCartModal" />

  <Home v-if="currentPage === 'Home'" @GoTo="section" />
  <About v-if="currentPage === 'About'" @GoTo="section" />
  <Contact v-if="currentPage === 'Contact'" />

  <Cardlist v-if="isCartOpen" :cart="cartItems" @close="closeModal" @update-quantity="updateCartQuantity"
    @remove-item="removeFromCart" @clear-cart="clearCart" @pay="payCart" />

  <Menupage v-if="currentPage === 'Menu'" @gotoMeal="filterCategory('Meals')" @gotoSnack="filterCategory('Snacks')"
    @gotoDrink="filterCategory('Drinks')" @gotoDessert="filterCategory('Dessert')" />

  <FoodCard v-if="currentPage === 'FoodCard'" :forFoods="filteredFoods" @close="currentPage = 'Menu'"
    @add-to-cart="addToCart" />

  <Footer @GoTo="section" />
</template>