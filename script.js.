// DesignHub - Main JavaScript

const products = [
  {
    id: 1,
    title: "Good Vibes Quote Design",
    category: "Posters",
    price: 499,
    description: "A bold typography poster for a creative workspace or social post.",
    rating: "4.9",
    reviews: 24,
    bg: "#f1e6d1",
    fg: "#14233a",
    art: "GOOD VIBES\nONLY",
    sub: "STUDIO NOTES / 01",
    symbol: "✦"
  },
  {
    id: 2,
    title: "Minimal Botanical Poster",
    category: "Posters",
    price: 399,
    description: "A clean botanical design with a modern minimal look.",
    rating: "4.8",
    reviews: 18,
    bg: "#dfe9df",
    fg: "#193126",
    art: "BOTANICAL\nSTUDIO",
    sub: "NATURE / 02",
    symbol: "❀"
  },
  {
    id: 3,
    title: "Lion King T-Shirt Design",
    category: "Branding",
    price: 599,
    description: "Bold lion artwork suitable for T-shirts and merchandise.",
    rating: "4.9",
    reviews: 32,
    bg: "#e7d4ad",
    fg: "#241b12",
    art: "LION\nKING",
    sub: "PREMIUM DESIGN / 03",
    symbol: "♛"
  },
  {
    id: 4,
    title: "Social Media Template Pack",
    category: "Social Media",
    price: 799,
    description: "Modern templates for Instagram, Facebook and other social platforms.",
    rating: "4.8",
    reviews: 21,
    bg: "#e1d9ee",
    fg: "#271d38",
    art: "SOCIAL\nPACK",
    sub: "CREATIVE KIT / 04",
    symbol: "✦"
  }
];

let cart = [];

const productGrid = document.querySelector("#productGrid");
const cartItems = document.querySelector("#cartItems");
const cartCount = document.querySelector("#cartCount");
const cartTotal = document.querySelector("#cartTotal");
const searchInput = document.querySelector("#searchInput");

function renderProducts(list = products) {
  if (!productGrid) return;

  productGrid.innerHTML = list.map(product => `
    <div class="product-card">
      <div class="product-art"
           style="background:${product.bg};color:${product.fg}">
        <span class="product-symbol">${product.symbol}</span>
        <div class="product-art-text">${product.art.replace(/\n/g, "<br>")}</div>
        <small>${product.sub}</small>
      </div>

      <div class="product-info">
        <span class="product-category">${product.category}</span>
        <h3>${product.title}</h3>
        <p>${product.description}</p>

        <div class="product-bottom">
          <strong>Rs. ${product.price}</strong>
          <span>⭐ ${product.rating} (${product.reviews})</span>
        </div>

        <button onclick="addToCart(${product.id})" class="btn">
          Add to Cart
        </button>
      </div>
    </div>
  `).join("");
}

function addToCart(id) {
  const product = products.find(p => p.id === id);

  if (!product) return;

  cart.push(product);
  updateCart();

  alert(`${product.title} cart mein add ho gaya!`);
}

function updateCart() {
  if (cartCount) {
    cartCount.textContent = cart.length;
  }

  if (cartTotal) {
    const total = cart.reduce((sum, item) => sum + item.price, 0);
    cartTotal.textContent = `Rs. ${total}`;
  }

  if (cartItems) {
    if (cart.length === 0) {
      cartItems.innerHTML = "<p>Your cart is empty.</p>";
      return;
    }

    cartItems.innerHTML = cart.map((item, index) => `
      <div class="cart-item">
        <div>
          <strong>${item.title}</strong>
          <p>Rs. ${item.price}</p>
        </div>
        <button onclick="removeFromCart(${index})">Remove</button>
      </div>
    `).join("");
  }
}

function removeFromCart(index) {
  cart.splice(index, 1);
  updateCart();
}

if (searchInput) {
  searchInput.addEventListener("input", function () {
    const keyword = this.value.toLowerCase().trim();

    const filtered = products.filter(product =>
      product.title.toLowerCase().includes(keyword) ||
      product.category.toLowerCase().includes(keyword)
    );

    renderProducts(filtered);
  });
}

document.addEventListener("DOMContentLoaded", function () {
  renderProducts();
  updateCart();
});
