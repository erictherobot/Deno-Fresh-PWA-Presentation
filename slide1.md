# DENO FRESH - PWA
By <a href="https://ericdavidsmith.com">Eric David Smith</a>

---

## TUTORIAL
Let's build a PWA in DENO FRESH

<img src="/deno-fresh.png" width="150"  />

---

## What is a PWA?
Progressive Web Apps (PWAs) are web apps that use service workers, manifests, and other web-platform features in combination with progressive enhancement to give users an experience similarly found with native apps.

---

## Is this for Mobile Only?
No. PWAs are built to take advantage of native mobile device features, without requiring the end user to visit an app store, make a purchase and download software locally.

---

## PWA Features & Capabilities

- Connectivity independence - low bandwidth
- App-like interface - mimic navigation of native
- Push notifications - user engagement
- Self-updates - stay fresh :)
- Safety / HTTPS only - Transport Layer Security (TLS)
- Discoverability and easy installation
- Works offline

---

## Prerequisites
- Install Deno CLI
- Create a new Deno Fresh App

---

## Install Deno CLI

    curl -fsSL https://deno.land/install.sh | sh

---

## Create new app
Deno Fresh App

```
deno run -A -r https://fresh.deno.dev deno-fresh-pwa
cd deno-fresh-pwa
deno task start
```

---

## Add `<Head />`
Open VSCode or another IDE and head over to the `index.tsx` and import the `<Head />` component from Deno Fresh like so 

```
import { Head } from "https://deno.land/x/fresh@1.0.1/runtime.ts";
```

---

## Add Manifest Link
Inside the same file `index.tsx`, add a reference to the manifest.webmanifest file. (we will create this soon)

```
<link
    crossOrigin="use-credentials"
    rel="manifest"
    href="/manifest.webmanifest"
/>
```

---

## Add PWA Script
Inside the same file `index.tsx`, add the following PWA script.

```
<script type="module">
    import 'https://cdn.jsdelivr.net/npm/@pwabuilder/pwaupdate/dist/pwa-update.js';
    const el = document.createElement('pwa-update');
        document.body.appendChild(el);
</script>
```

---

## Add manifest file
Inside your `/static` directory, create a new file called `manifest.manifest` or `manifest.json`. Then add the following code snippet to it. 

```json
{
  "name": "",
  "short_name": "",
  "theme_color": "#000000",
  "background_color": "#000000",
  "display": "fullscreen",
  "scope": "/",
  "start_url": "/",
  "orientation": "any",
  "icons": [
    {
      "src": "/icon-512x512.png",
      "sizes": "512x512",
      "type": "image/png"
    },
    {
      "src": "/manifest-icon-512.maskable.png",
      "sizes": "512x512",
      "type": "image/png",
      "purpose": "maskable"
    }
  ]
}
```

---

## Add Service Worker file
Inside your `/static` directory, create a new file called `pwa-sw.js`. Then add the following code snippet to it. https://gist.github.com/erictherobot/4cef30ba1edc184c88e454bf2dc71507

---

## Add Register Service Worker file
Inside your `/static` directory, create a new file called `pwa-sw-register.ts`. Then add the following code snippet to it. https://gist.github.com/erictherobot/5778631a1fcc72d45d5c18f5359a0809

---

## Add Assets
Inside your `/static` directory, create a set of new image / icon files.

```html
favicon.ico
icon-192x192.png
icon-256x256.png
icon-384x384.png
icon-512x512.png
manifest-icon-192.maskable.png
manifest-icon-512.maskable.png
```
You can use an online tool like https://realfavicongenerator.net which will give you all the assets needed from uploading a single image. 

---

## That's it!
You've created a Progressive Web App. 

Your users will thank you!

---

## Questions?
Contact <a href="https://ericdavidsmith.com">Eric David Smith</a> / <a href="https://twitter.com/erictherobot">@erictherobot</a>
