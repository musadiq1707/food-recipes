# 🍽️ Food Recipe

A Laravel package to fetch and manage recipes from third-party APIs with ease.  
It provides a simple, expressive interface to **search for recipes** and **fetch recipe details** from APIs like Spoonacular.  

---

## 🚀 Features
🔑 Easy API key configuration  
🍝 Search recipes by keyword  
📖 Get detailed recipe information by ID  
🛠️ Ready-to-use Facade (`Recipe`)  
✅ Built with Laravel best practices  

---

## 📦 Installation

Install the package via **Composer**:

```bash
composer require your-username/food-recipe
```
---

## ⚙️ Configuration
Publish the config file:
```bash
php artisan vendor:publish --tag=config --provider="YourNamespace\Recipes\RecipeServiceProvider"
```

This will create a `config/recipe.php` file.  
Add your API credentials in `.env`:

```bash
RECIPE_API_KEY=your_api_key_here
RECIPE_API_BASE_URL=https://api.spoonacular.com/recipes
```

## 🔥 Usage

You can use the Facade or inject the service directly.

**Search for recipes**

```php
use YourNamespace\Recipes\Facades\Recipe;

$recipes = Recipe::search('pasta');

dd($recipes);
```
**Get recipe by ID**

```php
$recipe = Recipe::getById(715538);

dd($recipe);
```
**Using Dependency Injection**
```php
use YourNamespace\Recipes\Services\RecipeClient;

public function index(RecipeClient $client)
{
    $recipes = $client->search('chicken');
    return view('recipes.index', compact('recipes'));
}
```

---

## 🤝 Contributing

Contributions are welcome!
Please fork the repository and submit a pull request.

## 📜 License

This package is open-source software licensed under the MIT license.
