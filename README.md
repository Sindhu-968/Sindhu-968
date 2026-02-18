---

## 🐍 Contribution Snake  

<p align="center">
  <img src="https://raw.githubusercontent.com/GASI SINDHUJA/YOUR_USERNAME/output/github-contribution-grid-snake.svg" alt="snake animation" />
</p>
<img src="https://raw.githubusercontent.com/gasisindhuja/gasisindhuja/output/github-contribution-grid-snake.svg" />
name: Generate Snake

on:
  schedule:
    - cron: "0 */12 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - uses: Platane/snk@v3
        with:
          github_user_name: YOUR_USERNAME
          outputs: |
            dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
