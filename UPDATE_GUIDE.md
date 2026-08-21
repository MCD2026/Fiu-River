# Fiu River stakeholder map — photo update guide

Stakeholder page: <https://mcd2026.github.io/Fiu-River/>

## Fast update from GitHub

1. Open the repository folder [`incoming-photos`](https://github.com/MCD2026/Fiu-River/tree/main/incoming-photos).
2. Select **Add file → Upload files**.
3. Drag in the new original geotagged JPG/JPEG photos.
4. Select **Commit changes** and commit directly to `main`.
5. Open the repository **Actions** tab and watch **Process New Site Photos**.
6. When that workflow and **Deploy GitHub Pages** are green, refresh the stakeholder page.

No QGIS, Forma, ACC login or local rebuild is required for routine photo additions.

## Photo requirements

- Use original files with GPS/location metadata.
- Do not use screenshots, WhatsApp copies or other versions that may have metadata removed.
- Filenames must be unique; existing filenames are treated as duplicates and skipped.
- Upload only new site-visit photos. The current photographs remain on the map automatically.

## What the automation changes

The workflow extracts each photo's coordinates and compass bearing, optimises a web copy, updates both datasets, extends the terrain cache if needed, verifies every image reference and republishes the existing URL.

The temporary originals are removed from `incoming-photos` after a successful rebuild. GitHub history still records the upload, while the live site contains optimised presentation copies.

## If the workflow is red

Open the failed **Process New Site Photos** run and read the failed step. The most common cause is a photo without GPS metadata. Remove or replace that file, then upload the corrected original again. The existing stakeholder site is not replaced when rebuilding fails.

## Optional local fallback

From a clean clone of the repository on Windows:

```powershell
powershell -ExecutionPolicy Bypass -File .\tools\Rebuild-FiuRiver.ps1 -Source "C:\SiteVisit\NewPhotos" -Publish
```

Use `-DryRun` first to check a folder without changing files. Use `-Replace` only when intentionally rebuilding the entire photo collection.
