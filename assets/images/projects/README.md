# Project Image Structure

Each project has its own folder under `assets/images/projects/<project-slug>/`.

Recommended naming:

- `cover.*`: main thumbnail or card background
- `preview.*`: hover preview image
- `screenshot.*` or `diagram-*.*`: detailed image for lightbox or documentation
- `legacy-*.*`: old assets kept temporarily for reference

When updating a project image:

1. Replace the file inside that project's folder.
2. Update the matching `media` path in `_data/projects.yml` if the filename changes.
3. No homepage template changes should be needed unless the project category changes.
