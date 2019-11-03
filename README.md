# Escaperoom
Tool om tipscherm + timer te maken voor escaperooms.
Werkt door middel van de [presentation API](https://developer.mozilla.org/en-US/docs/Web/API/Presentation_API), voorlopig dus alleen in Chrome.
## Benodigdheden:
- Deze code, gehost (met SSL)
  - www.scoutdash.nl/escaperoom/sender.html
- Laptop + 2e scherm (via kabel) óf Chromecast + scherm (telefoon met chromecast kan natuurlijk ook)

---------------
## lock.html
Voor onze escaperoom is het resultaat van een puzzel een 'wachtwoord' dat moet worden ingevuld op de computer. Als deze correct wordt ingevoerd worden plaatjes met aanwijzingen zichtbaar.
## videos.json
Plaats hierin een lijst met video's. Plaats de videobestanden (mp4) in de video's map. Deze video's worden zichtbaar als knop en kunnen met de knop worden afgespeeld.
### Voorbeeld
```json
{
	"videoButtons": [
		{
			"name": "intro",
			"key": "intro",
			"file": "videos/intro.mp4"
		},
		{
			"name": "Tussenstukje",
			"key": "tussenstuk",
			"file": "videos/tussenstuk.mp4"
		},
	]
}

```
Het jsonbestand is een object met de propperty "videoButtons". videoButtons is een array, voor elke video 1 item. Ieder item heeft de volgende props:
- name: de naam die wordt weergegeven in de knop
- key: unieke key voor de video's. Alleen letters, cijfers en streepjes.
- file: pad naar de video

Bij het openen van de sender.html zijn de video knoppen zichtbaar maar disabled. Na het verbinden worden de video's bij de receiver gepreloaded. Zodra de video geladen is, wordt de knop enabled. Klik op de knop om de video af te spelen. De knop wordt groen zodra deze speelt, als de video is afgelopen verdwijd de groene kleur. Als er een fout optreed bij het afspelen of preloaden van de video dan wordt de knop rood.
