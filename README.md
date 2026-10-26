# Kursblick

Persönliches Charting-Terminal als Ersatz für TradingView.

- Kerzencharts von 15 Minuten bis Monat, Tickersuche, Watchlist
- Klassische Indikatoren: SMA, EMA, VWAP, Volumen, RSI, MACD, Stochastik
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

Twelve Data kennt keine echten Indizes (dafür ETFs wie QQQ, SPY, IWM, VIXY); WTI-Öl gibt es erst ab dem Grow-Tarif.

## Technik

Eine einzelne Datei: `index.html`. Charts mit [TradingView Lightweight Charts](https://github.com/tradingview/lightweight-charts) 4.2.0 (Apache-2.0); das TradingView-Logo im Chart ist die von der Lizenz verlangte Namensnennung.
