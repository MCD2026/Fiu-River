# Upload new Fiu River photos here

Upload original `.jpg` or `.jpeg` photos into this folder using **Add file → Upload files** in GitHub.

Requirements:

- Upload the original files from the phone or camera.
- Location Services / GPS must have been enabled when the photos were taken.
- Do not send the files through an app that removes photo metadata.
- Keep each photo filename unique.

After committing the upload to `main`, GitHub automatically:

1. reads the GPS location, camera direction and altitude;
2. skips photos already present;
3. creates smaller presentation copies;
4. updates the 2D map and 3D tour;
5. refreshes terrain coverage when necessary;
6. removes the temporary originals from this folder; and
7. publishes the same stakeholder link.

The rebuild normally finishes within a few minutes. If a photo has no GPS metadata, the **Process New Site Photos** workflow will show a clear error and the existing stakeholder page will remain unchanged.
