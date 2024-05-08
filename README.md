# Repo-driven tag management

A simple PoC demonstrating how artifacts in a repo may update tags.

This repo just contains a copy of these actions as they were initially drafted.
They likely need to be adapted to fit your own use case.

## Concept

- On merge to the specified branches, action will read files in the
  **containertags/** directory. Filenames are tag names, and the content of each
  file should be a digest that exists in the container registry.

- GitHub Actions then tags each of the configured tags to the image digest
  stored in the file, so long as it exists.