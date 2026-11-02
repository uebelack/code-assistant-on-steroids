---
layout: cover
class: bg-horizon
colorSchema: dark
favicon: https://uebelacker.dev/favicon.ico
fonts:
  provider: none
  sans: 'Fira Code'
  serif: Orbitron
  mono: 'Fira Code'
---

# Code Assistant on Steroids

## Warum Entwickler nichts anderes brauchen

<div class="draft-badge">DRAFT</div>

<div class="absolute bottom-10">
  <span class="font-700">
    David Übelacker
  </span>
</div>

---

# Wer bin ich?

- **David Übelacker**
- Software Architect @ nag informatik ag in Basel
- 20+ Jahre Erfahrung in der Web- und Mobile-App-Entwicklung

<div class="absolute bottom-10">
  <div class="flex items-end">
    <img src="./images/nag.svg" class="logo-nag" style="width: 20%;" />
    <div style="width:45%"></div>
    <div style="width: 30%; display: flex; flex-direction: column; align-items: center;">
      <div class="qr-frame" style="width: 100%;"><img src="./images/qr.svg"/></div>
      <div>uebelacker.dev</div>
    </div>
  </div>
</div>

---

# Was wir anschauen

<div class="agenda-list">

1. TODO
2. TODO
3. TODO

</div>

---

# Alles ist Code

<div class="grid grid-cols-2 gap-x-12">
<div class="emoji-list">

- 🏗️ **Infrastruktur** — Terraform, Bicep
- 🔁 **Pipelines** — GitHub Actions
- ⚙️ **Konfiguration** — Helm, Ansible
- 📄 **Doku** — Markdown im Repo

</div>
<div class="emoji-list">

- 📊 **Diagramme** — Mermaid, PlantUML
- 🎞️ **Slides** — Slidev, Marp
- 🎬 **Video** — Remotion
- 🎵 **Musik** — Sonic Pi

</div>
</div>

<div class="compare-footer">zehn Jahre lang haben wir unsere Arbeit in Text in einem Repository verwandelt</div>

---
layout: two-cols-header
---

# Slides mit Slidev

::left::

- Markdown rein, Deck raus — **diese Slides sind dieses Repo**
- Vue und UnoCSS für alles, was mehr als Text braucht
- Code von shiki gehighlightet, Diagramme von mermaid
- `pnpm build` → eine statische Seite, deployt wie jede andere
- Reviewbar im Pull Request. Kein Binärklumpen, kein Drag and Drop

::right::

```md
# Alles ist Code

- Infrastruktur
- Pipelines
- Doku

<div class="big-quote">
Wenn es Text ist, ist es Code.
</div>
```

---

# Cloud, definiert in einer Datei

<div class="compare">
<div class="compare-col">
<div class="compare-head">Terraform</div>
<div class="compare-essence">terraform apply</div>
<ul>
<li>HCL, dieselbe Sprache für jeden Provider</li>
<li>der State weiss, was existiert</li>
<li>der Plan ist das Review</li>
</ul>
</div>
<div class="compare-col">
<div class="compare-head">AWS CDK</div>
<div class="compare-essence">cdk deploy</div>
<ul>
<li>TypeScript, Python, Java, Go</li>
<li>Schleifen und Typen statt Copy-Paste</li>
<li>erzeugt daraus CloudFormation</li>
</ul>
</div>
<div class="compare-col">
<div class="compare-head">Bicep</div>
<div class="compare-essence">az deployment group create</div>
<ul>
<li>Azures Antwort auf ARM-Templates</li>
<li>deklarativ, kein State zu pflegen</li>
<li>what-if, bevor Du es abschickst</li>
</ul>
</div>
</div>

<div class="compare-footer">der Assistent schreibt es, liest den Plan zurück und sagt Dir, was sich wirklich ändert</div>

---
layout: two-cols-header
---

# Video mit Remotion

::left::

- Ein Video **ist** eine React-Komponente
- Jedes Bild ist eine Funktion seiner Framenummer
- `npx remotion render` → ein mp4 aus der CI
- Text geändert? Neu rendern statt neu schneiden
- Promo-Clips, Release Notes, Erklärvideos

::right::

```tsx
export const Promo = () => {
  const frame = useCurrentFrame()
  const scale = spring({ frame, fps: 30 })

  return (
    <AbsoluteFill style={{ background: '#241b2f' }}>
      <h1 style={{ transform: `scale(${scale})` }}>
        Alles ist Code
      </h1>
    </AbsoluteFill>
  )
}
```

---
layout: two-cols-header
---

# Musik mit Sonic Pi

::left::

- Ein Synthesizer, live programmiert in Ruby
- `live_loop` lädt neu, während der Ton weiterläuft
- Deterministisch: die Datei ist die Aufnahme
- Intro-Musik, Stinger, ein Soundtrack für die Demo
- Der Assistent iteriert daran wie an jedem anderen Code

::right::

```ruby
live_loop :synthwave do
  use_synth :prophet
  play_chord chord(:e2, :minor7),
             release: 2, cutoff: 80
  sleep 2
end

live_loop :drums do
  sample :bd_tek, amp: 2
  sleep 0.5
end
```

---
layout: two-cols-header
---

# Keine API? Schreib eine.

::left::

- **proles** bucht unsere Stunden. Eine Web-App, keine öffentliche API
- Der Assistent hat den Browser-Traffic gelesen und den Client geschrieben
- `login`, `times`, `book`, `vacation`, `delete` — typisiertes TypeScript, ohne Build
- `--json` bei jedem Lesezugriff, damit der nächste Schritt wieder ein Prompt sein kann
- "Buch gestern, 8h, intern" statt zwölf Klicks

::right::

```bash
pnpm proles times --month 2026-10

pnpm proles book -a "nag intern" \
  -d yesterday -d today -H 8

pnpm proles vacation \
  -d 2026-12-23 --half morning

pnpm proles times --json | jq '.[].hours'
```

<div class="compare-footer">eine App ohne API ist eine App, um die noch niemand ein CLI gebaut hat</div>

---
layout: two-cols-header
---

# Dein Zuhause. Deine Rechner.

::left::

### homeassistant-bot

- Das `/config` der HA-Box als Spiegel in Git — Automationen werden diffbar
- Wöchentlich: Backup, alle offenen Updates einspielen, Core und OS zuletzt, Reboot falls nötig
- Sucht vor jedem Commit nach Secrets im Klartext und mailt den Report
- Cron am Freitagmorgen. Ich lese die Mail, nicht das Dashboard

::right::

### davconf

- Ein Repo für jede Maschine: brew, apt, zsh, Neovim, Ghostty, Karabiner
- `./update.sh` — derselbe Befehl zum Aufsetzen und zum Synchronhalten
- Die erste Shell des Tages synchronisiert im Hintergrund, einmal, abgekoppelt
- Die Macs bekommen alles; die headless Ubuntu-Box das, was ohne Bildschirm Sinn ergibt

---
layout: fact
---

# Vielen Dank!

<br/>

<div class="center">
<div class="qr-frame" style="width: 300px"><img src="./images/qr_repo.svg"/></div>
</div>

https://github.com/uebelack/code-assistant-on-steroids
