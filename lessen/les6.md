# Les 6

- [Les 6](#les-6)
  - [State Management](#state-management)
    - [Context API](#context-api)
  - [Opdracht 6.1 - Winkelmandje](#opdracht-61---winkelmandje)
  - [Eindopdracht](#eindopdracht)

<br><br>

## State Management

In complexe React-applicaties wordt het beheren van de state (gegevens) een steeds grotere uitdaging.

We hebben tot nu toe gebruik gemaakt van.

- Props doorgeven naar child componenten. Soms zelfs als de child elementen de prop zelf niet nodig hebben maar om het
  door te kunnen geven aan een dieper gelegen child component ("prop drilling").
- Lifting State Up, het laten beheren van een state door een parent component om deze te kunnen delen met een component
  op hetzelde niveau.
- Async storage om gegevens persistent op te slaan.

### Context API

De Context API is de oplossing van React voor het probleem van prop drilling. Het stelt je in staat om een state en/of
functies beschikbaar te stellen zonder dat je de props door hoeft te geven.

Dit werkt met drie onderdelen:

1.  **`createContext()`**: Hiermee maak je een nieuw Context-object.
2.  **`Provider`**: Dit component "levert" de state aan alle onderliggende componenten. Je wikkelt de `Provider` om de
    parent van de componenten die de state nodig hebben. De state wordt meegegeven via de `value` prop.
3.  **`useContext()`**: Dit is een hook waarmee een component zich kan "abonneren" op de state van een `Provider`. Het
    component zal automatisch opnieuw renderen als de state in de `Provider` verandert.

De Context API is ideaal voor "globale" state die op veel verschillende plekken in de app nodig is, zoals
thema-instellingen (light/dark mode), gebruikersgegevens, of de inhoud van een winkelmandje.

<br><br>

## Opdracht 6.1 - Winkelmandje

In deze opdracht bouw je een app met een `BottomTabNavigator` en een winkelmandje. De staat van het winkelmandje wordt
beheerd met de Context API, zodat zowel het productenscherm als het winkelmandscherm erbij kunnen.

[Installeer](../guides/installatie.md#les-2) een nieuwe Expo app en [installeer](../guides/installatie.md#les-6) een
**Bottom Tab Navigator**.

**Functionaliteiten**

1.  **Maak een Context voor het winkelmandje.**
    - Deze context moet de items in het mandje bijhouden.
    - Zorg voor functies om een product toe te voegen en te verwijderen.
2.  **Zet een `BottomTabNavigator` op met twee tabs:**
    - **Tab 1: "Producten"**
      - Toont een lijst (`FlatList`) met producten (minimaal 5, je mag ze zelf bedenken).
      - Elk product heeft een "Voeg toe aan mandje" knop.
      - Bij een klik op de knop wordt het product toegevoegd aan de winkelmand-context.
    - **Tab 2: "Winkelmand"**
      - Toont de producten die aan het mandje zijn toegevoegd (je hoeft producten niet te groeperen).
      - Toont het totaal aantal items in het mandje.
3.  **Gebruik de `Provider` op de juiste plek.**
    - Zorg ervoor dat de `Provider` de `BottomTabNavigator` omvat, zodat beide tabs toegang hebben tot de context.
4.  **Optioneel: Toon een badge op de "Winkelmand" tab.**
    - De badge moet het aantal items in het mandje weergeven. Deze moet live bijwerken wanneer je een product toevoegt
      op het productenscherm.

Nuttige links: [Context API](https://react.dev/reference/react/createContext),
[Bottom Tab Navigator](https://reactnavigation.org/docs/bottom-tab-navigator),
[Tab Bar met badge](https://reactnavigation.org/docs/bottom-tab-navigator#showing-a-badge-on-the-tab-bar-icon)
[Customizing Tab Bar](https://reactnavigation.org/docs/customizing-tabbar/)

## Eindopdracht

Ga verder met je eindopdracht.
