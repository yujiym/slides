# Slide repo build with [Slidev](https://github.com/slidevjs/slidev) hosted on Github Pages

## develop

- `pnpm install`
- `file=${filename} pnpm dev`
- visit <http://localhost:3030>
- edit `{filename}.md`

## build & deploy

- set `homepage` to `package.json`
- `file=${filename} pnpm run build`
- `file=${filename} pnpm run deploy`
- visit <`${homepage}/${filename}`>
  - e.g. `https://yujiym.github.io/slides/eth-meetup-tokyo-vol14/`
