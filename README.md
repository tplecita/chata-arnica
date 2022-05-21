# Chata Arnica
V tomto cvičení si zkusíme nastylovat předpřipravenou stránku fiktivního ubytování chata Arnica. Finální výsledek bude vypadat takto: 


## Seznámení se s projektem
Udělejte si **fork** tohoto repozitáře a naklonujte si ho k sobě. Pomocí `npx serve` si projekt spusťte.    

Prohlédněte si soubor `index.html` a `style.css`. Ve složce uvidíte několik souborů. Kromě složek s obrázky a ikonkami jsou tu soubory
- `index.html` - tady je html struktura projektu, není potřeba nijak upravovat, pouze si ji prohlédněte a všímejte si, jaké třídy jsou na jakých elementech. Část v html je zakomentovaná, ta je připravená pro bonusový úkol.
- `style.css` - tady jsou před připravené styly a sem také bude psát své styly
- `index.js` - tento soubor je připravený na bonusový úkol, teď není potřeba si ho všímat
- `toggle-switch.css` - tento soubor je připravený na bonusový úkol, teď není potřeba si ho všímat.

#### Připravené CSS
V souboru CSS vidíte připravené nějaké stylování, většinou marginy, paddingy a velikost fontů. Na začátku souboru je sekce **CSS variables**. V této sekci jsou definované barvy, které budeme v projektu používat. Použití proměnných v CSS je dobrá praktika, protože je možné si na začátku definovat nějaké hodnoty a ty potom pouze použít při stylování jednotlivých elementů.     

V CSS se proměnné definují většinou v základním elementu souboru, může to být samotný element `html` a nebo element `:root`. Proměnné definujeme takto: 
```css
html {
  --font-large: 2rem;
}
```
a používají se takto: 
```css
.section-title {
  font-size: var(--font-large);
}
```

**Při vlastním stylování vždy používejte připravené třídy. **

## Stylování pro mobil
V projektu děláme responzivní webovou stránku, proto začínáme stylovat mobile first.    
V CSS už je kromě nějakých stylů pro mobil připravené i media queries, proto své styly nezapomeňte psát v css souboru **nad** stylování pro desktop! 

#### Google fonts
Všimněte si, že v hlavičce souboru html jsou kromě `style.css` nalikované další styly. Tyto jsou stažené z fontů google. V projektu používáme tyto fonty: Alegreya Sans, Lora a Dawning of a New Day. Dokážete je najít v odkazu na google fonts? 

### Barva a styl textu: 
- Celému `body` nastavte barvu textu na barvu proměnné `--text`. 
- Nastavte také  `body` font-family na `'Alegreya Sans', sans-serif`. Druhá hodnota (sans-serif) značí font, který se má použít, pokud se nepodaří načtení prvního fontu. 
- Nastavte barvu `--text` také odkazům na sekce Ceník a Kontakt. 
- Nastavte font loga na ` 'Dawning of a New Day', cursive`
- Nastavte font hlavního nadpisu (`.pitch`) na `'Lora', serif`. Text vycentrujte. 

### Barva pozadí 
- Nastavte barvu pozadí `secondary` na hlavičku, sekci s úvodním nadpisem, sekci cenové nabídky a na patičku.
- Nastavte barvu pozadí `primary` na sekci s úvodním textem a sekci s recenzí. 

### Přidání obrázku 
- elementu `.intro-image` nastavte za pomocí `background-image` jako pozadí obrázek `arnica-intro.jpg`. Nezapomeňte uvést správnou cestu k obrázku ve složce images. 
- Výšku obrázku nastavte na 70% výšky displeje. 
- Obrázek vycentrujte a nastavte, aby pokrýval celou velikost elementu. Budou se vám k tomu hodit vlastnosti `background-size` a `background-cover`.

### Layout elementů
- prvky v hlavičce (`.page-header`) - logo a navigaci - nastylujte tak, že budou vedle sebe, vertikálně vycentrované a na horizonální ose budou na opačných koncích. 
- Nastavte maximální šířku úvodního textu (`.subheading-content`) na 800 pixelů a text vycentrujte. 
- Jednotlivé cenové nabídky (`.offer`) budou mít šířku 80% rodiče, ale maximálně mohou dosahovat šířky 270px.

### Recenze 
- Font textu recenze nastavte na _oblique_. 
- Na text recenze dejte 2px silný rámečer barvy `--secondary`. 

## Stylování pro desktop 
Jak v CSS vidíte, pro šířku nad 800px už je nějaké stylování připraveno.    
Do této sekce přidejte stylování od 800px:

### Cenové nabídky 
- Nastylujte cenové nabídky, tak aby byly vedle sebe, vertikálně zarovnané a byla mezi nimi mezera 3rem. 
- Jednotlivé cenové nabídky budou mít šířku 220px.

### Recenze 
- Zrušte rámeček na textu recenze, a místo něj nastavte pozadí na barvu `--secondary`. 
- Nastavte textu recenze šířku 250px
- elementu `.review__photo` nastavte za pomocí `background-image` jako pozadí obrázek `reviewer.jpg`. Nezapomeňte uvést správnou cestu k obrázku ve složce images. 
- Rozměry obrázku nastavte na šířku 300px a výšku 400px
- Obrázek vycentrujte a nastavte, aby pokrýval celou velikost elementu.
- Element s textem recenze posuňte o 60px doprava tak, aby zakrýval fotografii. Bude se vám k tomu hodit vlastnost `position. `

### Patička 
- Nastavte prvky v patičce (kontakt a odkazy na sociální media) tak, aby byly vedle sebe, vertikálně vycentrované a mezi nimi byla mezera 3rem. 

## Nad 1200px 
Pro šířku nad 1200px si vytvořte media query. 
- Nastylujte cenové nabídky a patičku tak, aby místo 3rem byla mezi prvky mezera 6rem. 

## Bonus
V bonusovém úkolu si zprovozníme překlikávání light a dark módu na stránce. 
- V souboru  `style.css` v sekci CSS variables si vytvořte nové proměnné, a to v elementu `:root[data-theme='dark']`. Tyto proměnné budou: 
  -  --background-primary: #132221;
  -  --background-secondary: #476462;
  -  --text: #e1e1e1; 
- V `index.html` si odkomentujte prvek `theme-switch-wrapper` a jeho obsah.  
- Do souboru `index.html` si napojte soubor `toggle-switch.css`a `index.js`. Nezapomeňte na typ `module`.
 V souboru `index.js` je odkaz na webovou stránku, která popisuje, jak funguje přepínání mezi light a dark modem. Stránku si pročtěte. 
- Pročtěte si `index.js` a okomentujte, co se děje v kódu. 
- Vyzkoušejte si, že přepínání funguje. 
- Naimplementujte ukládání preferencí light/dark módu do local storage podle článku (Store the user preference for future visits). 

 

