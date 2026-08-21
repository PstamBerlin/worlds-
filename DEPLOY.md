# Hosting worlds.peterstam.eu  (GitHub Pages + GoDaddy DNS)

Same setup as peterstam.eu: GitHub holds the files, GoDaddy holds the domain.
This folder is FLAT on purpose. Front door = index.html (the carousel).
The scrolling version is also here at /site.html.

Every file is now under GitHub's 25 MB web-upload limit, so no special tools needed.

## 1. Put the files on GitHub
- Make a new repo, e.g. PstamBerlin/worlds  (Public).
- Upload EVERYTHING in this folder (drag all files into the repo's upload page).
  Keep it flat — do not put them in a subfolder.
- The CNAME file (already here, contains "worlds.peterstam.eu") tells Pages the domain.

## 2. Turn on GitHub Pages
- Repo -> Settings -> Pages
- Source: Deploy from a branch -> Branch: main -> folder: / (root) -> Save.
- It will show "Your site is live at ..." after a minute.

## 3. Point the subdomain in GoDaddy
- GoDaddy -> your peterstam.eu domain -> DNS / Manage DNS.
- Add a record:
      Type:  CNAME
      Name:  worlds
      Value: pstamberlin.github.io
      TTL:   default (1 hour)
- Save. (Do NOT delete the records that run peterstam.eu itself.)

## 4. Finish
- Wait 15 min to ~1 hour for DNS.
- Back in GitHub Pages settings the custom domain check goes green -> tick
  "Enforce HTTPS".
- Open https://worlds.peterstam.eu  — done.

## Notes
- To change the front door to the scrolling version: copy site.html over index.html.
- operation-series.zip = 93 dossier PDFs (24 MB). picture-machines.zip = the Python
  tools + guides. picture-machine.html is the in-browser app; it needs no server.
- If you ever add a bigger download later, put it in a GitHub *Release* (2 GB limit)
  instead of the repo, and link to the release URL.
