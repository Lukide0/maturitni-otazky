# Creational patterns

## Singleton

Objekt, který může být instancován pouze jednou. Použijeme například u připojení k databázi nebo nastavení aplikace.

```php
  class Singleton
  {
      private static $instance = NULL;

      protected function __construct() { }

      public static function getInstance() : Singleton
      {
          if (self::$instance === NULL)
          {
              self::$instance = new static();
          }

          return self::$instance;
      }
  }
```

## Builder

Objekt se vytváří postupně a ne najednou.

```php
  class Burger
  {
      private $_bun;
      private $_ketchup;
      private $_salad;
      private $_meat;

      public function __construct(
          boolean $bun = false,
          boolean $ketchup = false,
          boolean $salad = false,
          boolean $meat = false)
      {
          $this->_bun = $bun;
          $this->_ketchup = $ketchup;
          $this->_salad = $salad;
          $this->_meat = $meat;
      }

      public function addBun() { $this->_bun = true; return $this; }
      public function addKetchup() { $this->_ketchup = true; return $this; }
      public function addSalad() { $this->_salad = true; return $this; }
      public function addMeat() { $this->_meat = true; return $this; }
  }

  // najednou (klasický způsob)
  $burgerA = new Burger(true, false, true, true);

  // postupně (použití builder patternu); $burgerA === $burgerB
  $burgerB = new Burger()->addBun()->addSalad()->addMeat();
```

## Prototype

Alternativa k dědění tříd. Rozdílem je, že dědíme přímo z objektu, a to i s jeho hodnotami.

```js
const zombie = {
  eatBrains() {
    return "Yum 🧠";
  },
};
zombie.eatBrains();

// Prototype
const zombieWithName = Object.create(zombie, { name: "Igor" });
zombieWithName.eatBrains();
zombieWithName.name;
```
