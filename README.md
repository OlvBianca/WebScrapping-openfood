# WebScrapping-openfood
Teste vaga de estágio

# Documentação

### O codigo abaixo funciona em qualquer produto do site
### Url do site https://br.openfoodfacts.org/
### O scrapping abaixo deverá ser rodado no console do navegador

```javascript
var productName = document.querySelector("h2.title-1").innerText.trim();
console.log(productName);

var nutritionalScore = document.querySelector('#attributes_grid li:first-child h4').innerText;

var ecoScore = document.querySelector('#attributes_grid li:nth-child(3) h4').innerText;

var ingredientsList = document.querySelectorAll("div.panel_text span");
var ingredients = [];
ingredientsList.forEach(function (ingredient) {
  ingredients.push(ingredient.innerText.trim() ? ingredient.innerText.trim() : "Sem ingredientes");
});

var htmlContent =
  "<h1>Nome do produto: " +
  productName +
  "</h1>" +
  "<h3>Pontuação nutricional: " +
  nutritionalScore +
  "</h3>" +
  "<h3>Ingredientes: " +
  ingredients.join(", ") +
  "</h3>" +
  "<h3>Eco Score:" +
  ecoScore +
  "</h3>";


var newWindow = window.open();
newWindow.document.open();
newWindow.document.write(htmlContent);
newWindow.document.close();

console.log("Nome do produto:", productName);
console.log("Pontuação nutricional:", nutritionalScore);
console.log("Ingredientes:", ingredients);
console.log("Eco Score:", ecoScore);

```
