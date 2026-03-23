# Les 1

- [Les 1](#les-1)
  - [JavaScript](#javascript)
  - [Opdracht 1.1 - Mini-puzzels](#opdracht-11---mini-puzzels)
  - [Frameworks](#frameworks)
    - [Opdracht 1.2 - React Mini](#opdracht-12---react-mini)

<br><br>

## JavaScript

**Onderwerpen om te herhalen:**

- Ternary & nullish coalescing operators
- Optional chaining
- Spread operator & rest parameters
- Destructuring Arrays & Objects
- Arrow functions & this scope
- Events
- Array & Object Iteration
- Promises
- Try/catch
- Fetch
- Await/async

<br><br>

## Opdracht 1.1 - Mini-puzzels

Deze opdracht bestaat uit een reeks **JavaScript mini-puzzels**, waarbij elke puzzel zich richt op een specifieke
techniek binnen JavaScript. Dit is een oefening om belangrijke concepten te herhalen en toe te passen in kleine,
gerichte codevoorbeelden.

<br>

**Werkwijze**

1. Kopieer de [startcode van de puzzels](../assets/puzzels.js) naar een eigen JavaScript-document.
2. Elke puzzel begint met een titel en een korte uitleg in **commentaar**.
3. Onder de uitleg staat `// Schrijf hier de code...`. **Vervang dit door jouw oplossing.**
4. Daaronder staan tot slot **console.logs** die de code testen. **Haal deze uit commentaar** om je oplossing te
   controleren.
5. Test je code door het bestand met node te starten (`node puzzels.js`).

<br><br>

## Frameworks

Frameworks zoals React (en Laravel) nemen veel werk uit handen bij het ontwikkelen van applicaties, doordat
standaardfunctionaliteiten automatisch voor je geregeld worden.

Je code draait binnen het framework, wat betekent dat je niet zelf je code (functies) aanroept maar dat deze door het
framework worden aangeroepen. Daarom moet je je aan de regels en conventies van het framework houden.

Soms wil je dat het framework specifieke taken voor je uitvoert die niet standaard worden afgehandeld. Hiervoor kun je
gebruik maken van _hooks_. Zoals `useState` om een waarde op te slaan en de applicatie automatisch te laten bijwerken
bij veranderingen. Of `useEffect` om code te laten uitvoeren op bepaalde momenten.

<br><br>

### Opdracht 1.2 - React Mini

Om meer inzicht te krijgen in de werking van een framework, ga je uitzoeken hoe een mini-framework gebaseerd op React
werkt, en ga je een hook-method schrijven voor dit framework.

Download de startcode, maar run het project nog niet: https://github.com/HR-CMGT/PRG07-react-mini

**Deel 1 - Verkennen framework**

1. Bekijk index.html. Wat is het id van de body? Kan je vinden waar dit id gebruikt wordt?
2. Zoek nu uit hoe het framework werkt. Dit doe je door de flow van het programma te volgen. Begin in het script
   main.js, en maak een tekening van de volgorde waarin functies aangeroepen worden en met welke argumenten.
3. Wat denk je dat het resultaat is?
4. Installeer de node modules (`npm install`) en run het project (`npm run dev`). Klopt je antwoord van vraag 3?

<br>

**Deel 2 - Elementen aanmaken**

1. React maakt gebruik van JSX. Onderwater creëren JSX-tags _elementen_ (m.b.v. de functie `createElement`) met een
   type (de html-tag), props (object met attributen), en eventuele children (child elementen of tekst content).
   React-mini heeft helaas nog geen JSX ondersteuning dus we moeten `createElement` zelf aanroepen om html en functie
   elementen te maken. Voeg aan de App een `main` toe met daarin een `section` met een `h2` en een `p` en voer hier
   tekst in.
2. Voeg ook een `button` toe met een alert. Tip: `onclick` is een property van button.
3. Maak nu een component aan genaamd `MyProfile`. Return hierin een `section` maakt met daarin een `h2` en een `p`. Zet
   in de **h1** een tekst als `Mijn profiel` en in de **p** een tekst als `Mijn naam is [NAAM]`, waarbij je `[NAAM]` meegeeft vanuit de `App` als prop. Voeg dit component toe
   aan de `App` in de `main`.

<br>

**Deel 3 - useState nabouwen**

1. Geef React-mini een `useState` functie die een initiële waarde als parameter verwacht en deze opslaat. Daarna
   returnt hij deze waarde. Maak vervolgens de variabele `counter` aan met jouw useState functie (dus:
   `const [counter, setCounter] = useState(0);`) aan het begin van de App-component om een counter in de App te tonen,
   die momenteel nog niet werkt maar altijd de initiele waarde 0 toont. NB. Omdat we alleen een waarde returnen, is
   `setCounter` nu nog `undefined`, dit ga je in de volgende stap implementeren.
2. Zorg nu dat je `useState` ook een setter returnt. Dit is een functie die de opgeslagen waarde verandert en daarna de
   functie `reRender` aanroept. Het is belangrijk dat de waarde niet in de functie `useState` zelf wordt opgeslagen,
   maar globaal (bedenk waarom!). Return naast de waarde nu ook de setter en gebruik deze om met de button de `count`
   op te hogen (`count + 1`).
3. Pas de setter aan zodat deze zowel een nieuwe waarde als een functie accepteert, vergelijkbaar met React.
   Bijvoorbeeld: (x) => x + 1.
4. Deze `useState` kan maar één waarde bijhouden. Denk na over hoe je `useState` voor meerdere variabelen zou kunnen
   werken. Je hoeft dit niet te programmeren, maar dat mag wel 😉
