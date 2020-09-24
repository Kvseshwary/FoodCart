<script>
   import Sides from 'sides.svelte';
	export let name;
	let src='image/pizza.jpg';
	let count=0;
	function handleClick() {
	count+=1;	
	}

let selected = Sides;
</script>

<main>
<ul>
  <li><a class="active" href="#home">Order</a></li>
  <li><a href="#offers">Offers</a></li>
  <li><a href="#rewards">Rewards</a></li>
  <li><a href="#contact">Contact Us</a></li>
</ul>
	<h1>Food Store</h1>
	<p><button>Pizza </button> <button>Sides </button><button>Dip </button><button>Dessert</button> <button>Drinks</button></p>
	 <div class="card">
      <img {src} alt="pizza" style="width:60%">
       <div class="container">
       <h4><b>Pizza</b></h4> 
       <p><button on:click={handleClick}>Add To Cart {count} {count === 1 ? 'Item' : 'Items'}</button></p> 
  </div>
</div>
  
  <svelte:component this={component: Sides}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
	.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  width: 20%;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

.container {
  padding: 2px 16px;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: Red;
}

li {
  float: left;
}

li a {
  display: block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover:not(.active) {
  background-color: #111;
}

.active {
  background-color: grey;
}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>