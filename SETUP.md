# System Activation & Setup: DEAD EYE GitHub Profile

This document outlines the step-by-step setup procedure required to activate the automated data-harvesting workflows for the **sivadst** profile.

## Prerequisite: Workflow Permissions

To allow the automated workflows (`snake.yml` and `profile-3d.yml`) to generate contribution graphics and push them back to your repository, you must grant write permissions to the GitHub Actions runner.

1. Navigate to your GitHub profile repository: `https://github.com/sivadst/sivadst`
2. Go to **Settings** > **Actions** > **General**.
3. Scroll down to the **Workflow permissions** section.
4. Select **Read and write permissions**.
5. Click **Save**.

---

## 1. Snake Grid Generation Workflow

The `snake.yml` workflow automatically runs every 12 hours (and on pushes to `main`). It executes the snake game generator and deploys the assets to a specialized `output` branch.

### Manual Verification / Initial Run
1. Go to the **Actions** tab of your repository.
2. Select **Generate Snake Animation** from the list of workflows on the left.
3. Click the **Run workflow** dropdown on the right and click the green **Run workflow** button.
4. Wait for the run to complete. It will create a new branch named `output` containing `github-contribution-grid-snake.svg` and `github-contribution-grid-snake.gif`.

### Enable GitHub Pages (Optional but Recommended)
To host the assets on GitHub Pages for high-speed serving:
1. Go to **Settings** > **Pages**.
2. Under **Build and deployment**, select **Deploy from a branch** as the source.
3. Under **Branch**, select `output` and folder `/ (root)`.
4. Click **Save**.
5. Once built, the SVG can be accessed at:
   `https://sivadst.github.io/sivadst/github-contribution-grid-snake.svg`

---

## 2. 3D Contribution Calendar Workflow

The `profile-3d.yml` workflow compiles a 3D visual map of your contributions nightly and commits it directly to the `main` branch.

### Initial Run
1. Go to the **Actions** tab of your repository.
2. Select **GitHub Profile 3D Contrib** from the list of workflows.
3. Click **Run workflow** and launch it.
4. Once completed, a new directory named `profile-3d-contrib/` will be created in the `main` branch, containing `profile-night-green.png`, which is rendered in your profile README.
