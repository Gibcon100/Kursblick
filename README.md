# Kursblick

Persönliches Charting-Terminal als Ersatz für TradingView.

- Kerzencharts von 15 Minuten bis Monat, Tickersuche
- Layout-Vorlagen: Indikatoren, Einstellungen und Zeitrahmen unter einem Namen speichern und mit einem Klick wechseln ("Mein Standard (30m)" ist vorinstalliert)
- Mehrere Watchlists mit Abschnitten, Kurs und Tagesänderung; Import aus TradingView (.txt-Export) und aus IBKR-Watchlists, Export zurück ins TradingView-Format
- Echte Indizes (NDX, SPX, Dow, RUT, VIX) und fortlaufende Futures (NQ1!, ES1!, CL1!, GC1!, SI1! …) über Interactive Brokers, mit automatischem Kontraktwechsel
- Klassische Indikatoren: SMA, EMA, VWAP, Volumen, RSI, MACD, Stochastik, SuperTrend, Ichimoku, Keltner, Donchian, ATR, ADX/DMI, OBV
- Eigene Indikatoren, nachgebaut aus TradingView:
  - CM_Ult_MacD_MTF (ChrisMoody)
  - SQZMOM_LB – Squeeze Momentum (LazyBear)
  - CM_Ultimate_MA_MTF_V2 (ChrisMoody)
  - Bollinger Bänder mit Füllung
- Zeichenwerkzeuge: horizontale Linie, Trendlinie, Fibonacci-Retracement, Rechteck, Text, Rückgängig
- Preisalarme: Preis im Chart anklicken; Hinweis mit Ton, solange die Seite offen ist
- Chart aktualisiert sich jede Minute
- Firmen-Panel mit Profil, Bewertung und Fundamentaldaten

## Daten

Kurse und Firmendaten kommen über den Twelve-Data-Connector von claude.ai. Die Seite läuft als claude.ai-Artifact und fragt die Daten mit dem Konto des Betrachters ab, es liegt kein API-Schlüssel im Code. Ohne Connector zeigt sie Beispieldaten.

Twelve Data kennt keine echten Indizes (dafür ETFs wie QQQ, SPY, IWM, VIXY); WTI-Öl gibt es erst ab dem Grow-Tarif. Deshalb kommen Indizes, Futures und die Kurse in der Watchlist über den Interactive-Brokers-Connector (ohne Echtzeit-Abo 10 bis 15 Minuten verzögert). Watchlists, Zeichnungen und Alarme liegen im Browser (localStorage).

## Technik

Eine einzelne Datei: `index.html`. Charts mit [TradingView Lightweight Charts](https://github.com/tradingview/lightweight-charts) 4.2.0 (Apache-2.0); das TradingView-Logo im Chart ist die von der Lizenz verlangte Namensnennung.
- Mehrfach-Charts: oben rechts im Chart-Kopf 1, 2 oder 4 Charts wählen. Neben dem Hauptchart (mit allen Indikatoren) erscheinen 1 bzw. 3 kompakte Charts, jeweils mit eigenem Wert (aus der aktuellen Watchlist) und eigenem Zeitrahmen. Der Pfeil lädt den Wert in den Hauptchart. Die Auswahl bleibt im Browser gespeichert.
