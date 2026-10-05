# 4th PMD Ontology Hackathon website

Bilingual static website for the 4th PMD Hackathon, hosted by BAM in Berlin from 18 to 20 November 2026.

## Repository structure

```text
.github/workflows/pages.yml       Build PDF and deploy GitHub Pages
site/                             Public website (English at root)
  de/                             German version
  assets/css/                     Styles
  assets/js/                      Small progressive enhancements
  assets/images/                  BAM and MaterialDigital logos
  assets/resources/               Public downloads
protocol/protocol.md              Current HackMD export / protocol source
resources/agenda/                 Source copy of the official agenda
resources/results/                Public outputs created during the hackathon
```

## Publish the site

1. Create the repository `materialdigital/ontology-hackathon-4`.
2. Push this folder to the `main` branch.
3. In **Settings → Pages → Build and deployment**, select **GitHub Actions**.
4. Run the workflow once or push a change.
5. The English site will be available at `https://materialdigital.github.io/ontology-hackathon-4/`; German is at `/de/`.

## Update the protocol and generated PDF

1. Export the current HackMD document as Markdown.
2. Rename the export to `protocol.md`.
3. Replace `protocol/protocol.md` and commit the change.
4. GitHub Actions converts it to `site/assets/resources/hackathon-protocol.pdf` and deploys the updated site.

The live HackMD edit link remains the collaborative source. The repository copy is a dated snapshot used for publication and PDF generation.

## Update resources

- Replace `resources/agenda/Agenda_Hackathon_4.pdf` for the archival source.
- Also replace `site/assets/resources/Agenda_Hackathon_4.pdf` so the website serves the new version.
- Add workshop outputs to `resources/results/`. If they should be downloadable from the website, copy them into `site/assets/resources/` and add a link in both language pages.

## Local preview

```bash
python -m http.server 8000 --directory site
```

Then open `http://localhost:8000/`.

## Notes

- The site uses plain HTML, CSS and minimal JavaScript. No framework or build step is required for local development.
- The supplied logos remain the property of their respective organisations and should be used according to their design and usage rules.
- Review the event details, accessibility and legal requirements before public launch.
