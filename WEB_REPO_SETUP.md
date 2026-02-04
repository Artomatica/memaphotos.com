# Web Directory Setup

The `web/` directory is managed as a **separate git repository** pointing to the memaphotos.com GitHub Pages site.

## Repository Structure

- **Main Repository**: `/home/andrii/Projects/memaPhoto` (memaPhoto app)
  - Contains React Native app code, docs, and project files
  - `web/` directory is gitignored (managed separately)

- **Web Repository**: `/home/andrii/Projects/memaPhoto/web` (memaphotos.com website)
  - Separate git repository: `git@github.com:Artomatica/memaphotos.com.git`
  - Deployed to GitHub Pages at https://memaphotos.com
  - Contains landing page, privacy policy, support page

## Working with the Web Directory

### Making Changes to the Website

```bash
cd web
# Make your changes to index.html, privacy.html, etc.
git add .
git commit -m "Update website content"
git push origin main
```

Changes will be live at https://memaphotos.com within a few minutes.

### Pulling Latest Website Changes

```bash
cd web
git pull origin main
```

### Checking Website Status

```bash
cd web
git status
git log --oneline -5
```

## Benefits of This Setup

1. **Separate Deployment**: Website can be updated independently of the app
2. **Clean History**: Web changes don't clutter the main app repository
3. **GitHub Pages**: Automatic deployment when pushing to main branch
4. **Easy Collaboration**: Web designers can work on the site without touching app code

## Important Notes

- The `web/` directory is **not** a git submodule (those are complex)
- It's simply a separate git repository nested inside the main project
- The main repo ignores `web/` via `.gitignore`
- Both repositories are independent and can be managed separately
