#### Entwicklung eines Chat SaaS mit Kubernetes in Gaia-X kompatibler Cloud

Bachelorarbeit von Lukas Höhl

---

## Inhaltsverzeichnis 

1. Grundlagen
   1. Kubernetes
   2. Gaia-X
   3. Software as a Service (SaaS)
2. Komponenten des Chat SaaS
3. Einbindung in Gaia-X Cloud
4. Datenschutz
5. Ausblick

---

## Grundlagen
- SaaS Plattform soll als Containerbasierte Lösung betrieben werden
- Kubernetes dient als Orchestrator der Container

---

### Kubernetes

- Seit 2014 als Open Source Containerorchestrationstool verfügbar
- Entwicklung beginnt bei Google
- Zusammenschluss von "Worker Machines" zu einem Cluster
- Definition von Workloads durch "Objekte"
  - Verschiedene Arten von Objekten wie Pods, Services, Deployment

---

### Gaia-X

- europäische Initiative für einen freien Software Stack
  - Kontrolle
  - Governance 
  - Erstellung gemeinsamer Regeln sowie Richtlinien
- Ziel: **Cloudsouveränität**
- anwendbar auf bestehenden Cloudstrukturen

---

#### Prinzipien von Gaia-X
- Föderationen
  - Autonomität innerhalb der Cloud
  - Infrastrukturen auf vertrauensvolle Weise miteinander verbinden
- Dezentralisierung
  - Selbstorgranisation innerhalb der Föderation
- Offenheit
  - Einfaches Hinzufügen, Entfernen sowie Verändern von Komponenten

---

### Software as a Service (SaaS)
- Bereitstellung einer Standardlösung durch den Betreiber für Tenants (Kunden)
- Beispiel: Google Docs

---

## Komponenten des Chat SaaS
- verteilte Architektur
<!-- TODO: Bild einfügen -->

---

### Operator
<!-- TODO: Bild einfügen -->
- Erweiterung der Kubernetes API mit eigenem Objekt
  - Objekt dient als API Schnittstelle für andere Systeme
- Erstellung von Objekten für Chat Anwendung im Kubernetes Cluster

---

### Tenant Service
- Konfiguration der einzelnen Kunden im Kubernetes Cluster
  - eigener *Namespace* im Cluster -> Isolation von anderen *Tenants*
  - Zertifikatsherausgeber für SSL Verbindungen

---

### Rocket API Service
- Vereinfachung der Erstellung des Operator Objekts
- OIDC Protokoll für Authentifizierung
  - Keycloak
  - Zuordnen von Tenants im Cluster via OpenID Token

---

## Einbindung in Gaia-X
- Basis der Gaia-X Infrastruktur: **Soveign Cloud Stack**
- Föderationskatalog, in dem Anbieter ihre Services listen können
- Lifecycle Managment Engine
  - Nutzer des Service gibt gewünschte Konfiguration an
  - Engine kümmert sich um die Erstellung des Services
<!-- TODO: Bild einfügen für LCM Engine Workflow -->

---

### Soveign Cloud Stack
- Freier Software Stack
- Nutzen durch Cloudprovider um Gaia-X konforme Infrastruktur zu erstellen
- Basiert auf OpenStack
- Aktuell noch nicht vollständig implementiert
  - Infrastruktur as a Service

---

## Datenschutz
- Gefährdung von europäischen Datenschutz durch **US Cloud Act**
<!-- TODO: Note für US Cloud ACt -->
- Gaia-X Richtlinien zu Datenschutz:
  - strenge Bindung an Kundenvorgaben
  - Klare Definition wie Vorgaben gestellt werden
  - Explizite Angabe bei Datenweitergabe an Dritte
  - Angabe von Unterauftragsverarbeitern von Daten
- Artikel 26 und 28 der Datenschutz Grundverordnung müssen eingehalten werden!
<!-- TODO: Recherchieren von den Artikeln und als Note hinzugeben -->

---

## Fazit
- SaaS Implementierung für Gaia-X Cloud schon möglich
- Gaia-X Standard sowie SCS fehlt es an Reife und Services
  - aktuell nur Infrastuktur Services
- Kubernetes als attraktive Plattform für SaaS Anwendungen

---

## Ausblick
- Gaia-X steht aktuell noch in den Startlöchern
  - Vollständige Implementation von allen Services soll 2023 fertiggestellt sein
- Globale Konkurrenz für Hyperscaler Clouds wie **AWS**, **GCP** oder **Azure** frühstens 2025


