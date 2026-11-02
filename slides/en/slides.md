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

## Why Developers Don't Need Anything Else

<div class="draft-badge">DRAFT</div>

<div class="absolute bottom-10">
  <span class="font-700">
    David Übelacker
  </span>
</div>

---

# Who am I?

- **David Übelacker**
- Software Architect @ nag informatik ag in Basel
- 20+ years of experience in web and mobile app development

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

# Where we're going

<div class="agenda-list">

1. TODO
2. TODO
3. TODO

</div>

---

# Everything as code

<div class="grid grid-cols-2 gap-x-12">
<div class="emoji-list">

- 🏗️ **Infrastructure** — Terraform, Bicep
- 🔁 **Pipelines** — GitHub Actions
- ⚙️ **Configuration** — Helm, Ansible
- 📄 **Docs** — Markdown in the repo

</div>
<div class="emoji-list">

- 📊 **Diagrams** — Mermaid, PlantUML
- 🎞️ **Slides** — Slidev, Marp
- 🎬 **Video** — Remotion
- 🎵 **Music** — Sonic Pi

</div>
</div>

<div class="compare-footer">ten years of turning our work into text in a repository</div>

---
layout: two-cols-header
---

# Slides with Slidev

::left::

- Markdown in, deck out — **these slides are this repo**
- Vue and UnoCSS for the slides that need more than prose
- Code highlighted by shiki, diagrams by mermaid
- `pnpm build` → a static site, deployed like any other
- Reviewable in a pull request. No binary blob, no drag and drop

::right::

```md
# Everything as code

- Infrastructure
- Pipelines
- Docs

<div class="big-quote">
If it is text, it is code.
</div>
```

---

# Cloud, defined in a file

<div class="compare">
<div class="compare-col">
<div class="compare-head">Terraform</div>
<div class="compare-essence">terraform apply</div>
<ul>
<li>HCL, same language for every provider</li>
<li>state file knows what exists</li>
<li>the plan is the review</li>
</ul>
</div>
<div class="compare-col">
<div class="compare-head">AWS CDK</div>
<div class="compare-essence">cdk deploy</div>
<ul>
<li>TypeScript, Python, Java, Go</li>
<li>loops and types instead of copy-paste</li>
<li>synthesises to CloudFormation</li>
</ul>
</div>
<div class="compare-col">
<div class="compare-head">Bicep</div>
<div class="compare-essence">az deployment group create</div>
<ul>
<li>Azure's answer to ARM templates</li>
<li>declarative, no state to keep</li>
<li>what-if before you commit</li>
</ul>
</div>
</div>

<div class="compare-footer">the assistant writes it, reads the plan back and tells you what will actually change</div>

---
layout: two-cols-header
---

# Video with Remotion

::left::

- A video **is** a React component
- Every frame is a function of its frame number
- `npx remotion render` → an mp4 out of CI
- Copy changed? Re-render, don't re-edit
- Promo clips, release notes, explainers

::right::

```tsx
export const Promo = () => {
  const frame = useCurrentFrame()
  const scale = spring({ frame, fps: 30 })

  return (
    <AbsoluteFill style={{ background: '#241b2f' }}>
      <h1 style={{ transform: `scale(${scale})` }}>
        Everything as code
      </h1>
    </AbsoluteFill>
  )
}
```

---
layout: two-cols-header
---

# Music with Sonic Pi

::left::

- A live-coded synth, programmed in Ruby
- `live_loop` reloads while the sound keeps playing
- Deterministic: the file is the recording
- Intro music, stingers, a soundtrack for the demo
- The assistant iterates on it like any other code

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

# No API? Write one.

::left::

- **proles** books our hours. A web app, no public API
- The assistant read the browser traffic and wrote the client
- `login`, `times`, `book`, `vacation`, `delete` — typed TypeScript, no build step
- `--json` on every read, so the next step can be a prompt again
- "Book yesterday, 8h, internal work" instead of twelve clicks

::right::

```bash
pnpm proles times --month 2026-10

pnpm proles book -a "nag intern" \
  -d yesterday -d today -H 8

pnpm proles vacation \
  -d 2026-12-23 --half morning

pnpm proles times --json | jq '.[].hours'
```

<div class="compare-footer">an app without an API is an app nobody has wrapped yet</div>

---
layout: two-cols-header
---

# Your home. Your machines.

::left::

### homeassistant-bot

- The HA box's `/config` mirrored into git — automations become diffable
- Weekly job: back up, install every pending update, Core and OS last, reboot if needed
- Scans for plaintext secrets before it commits, mails the report
- Cron on Friday morning. I read the mail, not the dashboard

::right::

### davconf

- One repo for every machine: brew, apt, zsh, Neovim, Ghostty, Karabiner
- `./update.sh` — the same command to set a machine up and to keep it in sync
- The first shell of the day re-syncs in the background, once, detached
- Macs get everything; the headless Ubuntu box gets what means something without a screen

---
layout: fact
---

# Thank you!

<br/>

<div class="center">
<div class="qr-frame" style="width: 300px"><img src="./images/qr_repo.svg"/></div>
</div>

https://github.com/uebelack/code-assistant-on-steroids
