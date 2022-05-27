# Portfolio

🚀 A Prebuilt portfolio website for developers and online creators made with Javascript and Vue.js can be modified with JSON.

[![DigitalOcean Referral Badge](https://web-platforms.sfo2.digitaloceanspaces.com/WWW/Badge%203.svg)](https://www.digitalocean.com/?refcode=5d09deecbc5d&utm_campaign=Referral_Invite&utm_medium=Referral_Program&utm_source=badge)

![Image](DELETEME/preview.png)

## Installation

- First we'll clone this repository to our local machine, if you don't have the git CLI just download the repository.
- Once we have the cloned repository we'll install the required node modules.
- Wait for a while, after all the required modules are installed, we'll edit the JSON inside `/src/builder.js` to our liking.
- Now once we're done, we'll build for production and have our files in the `/dist` directory.

```shell
## Download
git clone https://github.com/jareer12/portfolio.git Portfolio
## Open Directory
cd Portfolio
## Install Modules
npm install
## Edit /src/builder.js
nano ./src/builder.js
## Build for Production
npm run build
```

## Themes

The portfolio comes with 5 prebuilt themes. Change the `theme` option in `/src/builder.js` to change the website theme. To change/edit these themes open `./tailwinds.config.js` and edit the heximal codes from there and run `npm run css` to rebuild the css once css is compiled build the app for production again(shown above).

- `brew` - DodgerBlue
- `royal` - Orange
- `emerald` - Green
- `amethyst` - Pink
- `valencia` - Red
