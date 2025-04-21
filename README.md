# one-style---site
<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>OneStyle - Loja de Roupas</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <h1>OneStyle</h1>
    <nav>
      <a href="#produtos">Produtos</a>
      <a href="#contato">Contato</a>
      <button onclick="toggleCart()">Carrinho (<span id="cart-count">0</span>)</button>
    </nav>
  </header>

  <section id="hero">
    <h2>Moda urbana, confortável e acessível.</h2>
    <p>Descubra os lançamentos da OneStyle</p>
    <a href="#produtos" class="btn">Ver Produtos</a>
  </section>

  <section id="produtos">
    <h2>Produtos</h2>
    <div class="produtos-grid">
      <div class="produto">
        <img src="https://via.placeholder.com/200" alt="Camiseta Básica" />
        <h3>Camiseta Básica</h3>
        <p>R$ 59,90</p>
        <button onclick="addToCart('Camiseta Básica', 59.90)">Comprar</button>
      </div>
      <div class="produto">
        <img src="https://via.placeholder.com/200" alt="Moletom Oversized" />
        <h3>Moletom Oversized</h3>
        <p>R$ 129,90</p>
        <button onclick="addToCart('Moletom Oversized', 129.90)">Comprar</button>
      </div>
      <div class="produto">
        <img src="https://via.placeholder.com/200" alt="Calça Cargo" />
        <h3>Calça Cargo</h3>
        <p>R$ 99,90</p>
        <button onclick="addToCart('Calça Cargo', 99.90)">Comprar</button>
      </div>
    </div>
  </section>

  <section id="contato">
    <h2>Fale com a gente</h2>
    <form>
      <input type="text" placeholder="Seu nome" required />
      <input type="email" placeholder="Seu e-mail" required />
      <textarea placeholder="Mensagem" required></textarea>
      <button type="submit">Enviar</button>
    </form>
  </section>

  <div id="cart" class="hidden">
    <h3>Seu Carrinho</h3>
    <ul id="cart-items"></ul>
    <p>Total: R$ <span id="total">0.00</span></p>
    <button onclick="checkout()">Finalizar Compra</button>
  </div>

  <footer>
    <p>&copy; 2025 OneStyle. Todos os direitos reservados.</p>
  </footer>

  <script src="script.js"></script>
</body>
</html>

body {
  margin: 0;
  font-family: 'Segoe UI', sans-serif;
  color: #333;
  background-color: #f5f5f5;
}

header {
  background-color: #000;
  color: #fff;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav a, nav button {
  margin: 0 10px;
  color: #fff;
  text-decoration: none;
  background: none;
  border: none;
  cursor: pointer;
  font-size: 1em;
}

#hero {
  background: url('https://via.placeholder.com/1400x500') center/cover no-repeat;
  color: white;
  text-align: center;
  padding: 100px 20px;
}

#hero .btn {
  background-color: #ff4d4d;
  color: white;
  padding: 10px 20px;
  border: none;
  text-decoration: none;
  margin-top: 20px;
  display: inline-block;
  font-weight: bold;
}

#produtos {
  padding: 50px 20px;
  background-color: #fff;
}

.produtos-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 20px;
}

.produto {
  background: #fafafa;
  padding: 15px;
  border-radius: 8px;
  text-align: center;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.produto img {
  max-width: 100%;
  height: auto;
}

.produto button {
  margin-top: 10px;
  background-color: #000;
  color: white;
  border: none;
  padding: 10px;
  cursor: pointer;
}

#contato {
  padding: 40px 20px;
  background: #eee;
}

#contato form {
  max-width: 400px;
  margin: auto;
  display: flex;
  flex-direction: column;
}

#contato input, #contato textarea {
  margin-bottom: 15px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

#cart {
  position: fixed;
  right: 20px;
  top: 80px;
  background: white;
  border: 1px solid #ddd;
  padding: 15px;
  width: 300px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.2);
  display: none;
}

#cart.hidden {
  display: none;
}

footer {
  text-align: center;
  padding: 20px;
  background: #000;
  color: #fff;
}
