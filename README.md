# co2Card

A custom Lovelace card for Home Assistant that checks if CO2 content is in a good range for current grow light PPFD. It has a nice CO2 atom indicator ;)

First try writing a custom card. I know it's not perfect. Any contributions, recommendations and comments are welcome!

Base data used in script:

|    PPFD        | CO2 (ppm)  |
| -------------- | -----------|
|    200-450     |     400    |
|    450-800     |     800    |
|   800-1000     |    1400    |
|   1000-1400 	 |  > 1400    |


## Screenshot

![Screenshot](https://raw.githubusercontent.com/maziggy/co2Card/refs/heads/main/screenshots/co2CardGreen2.png)

![Screenshot](https://raw.githubusercontent.com/maziggy/co2Card/refs/heads/main/screenshots/co2CardYellow.png)

![Screenshot](https://raw.githubusercontent.com/maziggy/co2Card/refs/heads/main/screenshots/co2CardRed.png)

## Installation

### Via HACS

1. Ensure you have [HACS](https://hacs.xyz/) installed.
2. In Home Assistant, go to **HACS** > **Frontend**.
3. Click the **"+"** button to add a new repository.
4. Enter the repository URL: `https://github.com/maziggy/hassCo2Card.git`.
5. Select **Dashboard** as the category and **Save**.
6. Once installed, add the card to your Lovelace dashboard.

or simply

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Martin+Ziegler&repository=https%3A%2F%2Fgithub.com%2Fmaziggy%2FhassCo2Card.git&category=Dashboard)

## Configuration


```yaml
  type: custom:co2Card
  entity: sensor.growbox_water_tds
  entity_ppfd: input_number.grow_ppfd
  rangeGreen: 100 # ppm difference to desired value | in range
  rangeYellow: 200 # ppm difference to desired value | slightly out of range
  theme:
    bgColor: "#2c2c2e"
    textColor: "#fff"
    textColorBubble: "#fff"
    iconColor: "#ff9e32"
