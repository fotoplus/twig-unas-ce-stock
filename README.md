# Termékek telephelyi (raktári) elérhetőség megjelenítése UNAS webáruházban (TWIG)


A `_stock_info.html` fájlt egy `{% include 'stock_info.html' %}` -el lehet elhelyezni a `content_product_details_[n].html` termék oldalon.
A `main.cfg` fájlban a `shop_config` részben a `text_custom_names` részben lehet beállítani az egyedi szövegek neveit a készletinformáció előtti szövegre, a többi kulcsú elemet pedig a raktárak nevére és a kiegészítő információra.
Szintén a `main.cfg` fájlban a `common_vars` részben a `params` kulcs alatt lehet beállítani a raktárakhoz tartozó készletinformációkhoz tartozó paramétereket.
A kapcsolódó CSS-t hozzá kell adni vagy a saját CSS-hez, vagy a sablon SCSS fájljához.


**main.cfg**
```json
 "shop_config": {
        "text_custom_names": {
            "10": "Készletinfo előtti szöveg",
            "11": "Készletinfo: 1. raktár neve",
            "12": "Készletinfo: 1. raktár kiegészítő információ",
            "13": "Készletinfo: 2. raktár neve",
            "14": "Készletinfo: 2. raktár kiegészítő információ",
            "15": "Készletinfo: 3. raktár neve",
            "16": "Készletinfo: 3. raktár kiegészítő információ",
        }
    },
```
**main.cfg**
```json

  "common_vars": {
        "params": { 
            "keszlet_raktar1":	"000000",
            "keszlet_raktar2":	"000000",
            "keszlet_raktar3":	"000000"
        },

```

**CSS**
```css

/* Készlet */
.fp-stock-info-container {
  display: block;
  margin: 5px 0 5px 0;
}

.fp-stock-info {
  padding: 0px;
  margin: 2px;
}

.fp-stock-info-title {
  display: block;
  font-weight: bold;
}

.fp-stock-info-badge {
  display: inline-block;
  background-color: transparent;
}

.fp-stock-info-text {
  color: gray;
  font-weight: normal;
}

.fp-red {
  color: var(--red);
}

.fp-green {
  color: var(--green);
}

```


