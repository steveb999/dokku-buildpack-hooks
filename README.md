# Dokku Buildpack Hooks

A tiny Dokku / Herokuish buildpack that lets you run custom scripts **before other buildpacks execute**.  
Useful for generating data, pulling external content, transforming CSV → JSON, etc — *before* a static site or app is built.

---

## What This Buildpack Does

During the build phase this buildpack will:

1️⃣ Check if your app repo contains `bin/pre-build`  
2️⃣ If present and executable → **it runs it**  
3️⃣ If missing → it safely skips

Nothing else is changed. No runtime services. No Procfile requirements. No web config.

---

## Installation / Usage

Add this buildpack *first* in your `.buildpacks` file, before Hugo / Nginx / Node / etc:

