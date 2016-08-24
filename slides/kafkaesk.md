### Configuration@Kafkaesk

<!-- .slide: data-background="img/background-orange-orig.jpg" -->

---
### Regeln

- Konfiguration ist in git-Repository hinterlegt (kafkaesk-dev-config, kafkaesk-prod-config)
- globale Einstellungen in die `application.yml`
- Jeder Service wird benannt nach Schema `${stream}-${service}` (z.B. `imported-bons-producer`)
- Spezifische Konfiguration nach `${stream}-${service}.yml`

---
### Konfiguration verteilen

- Dateien ändern, comitten und pushen
- betreffenden Service neu starten
