# HOW TO RUN PUPPETEER ON SERVERS

As a guide for myself and others who may want to run puppeteer on a server, I have created this guide.

1. The packages needed to run puppeteer on a server are:

```
sudo apt-get update

sudo apt-get install -y gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils wget npm
```

2. We should add nosandbox to the puppeteer launch options:

```
const browser = await puppeteer.launch
({args: ['--no-sandbox', '--disable-setuid-sandbox']});
```

3. If we are running on a non headless run this instead

```
apt install -y gconf-service libasound2 libatk1.0-0 libc6 libcairo2 libcups2 libdbus-1-3 libexpat1 libfontconfig1 libgcc1 libgconf-2-4 libgdk-pixbuf2.0-0 libglib2.0-0 libgtk-3-0 libnspr4 libpango-1.0-0 libpangocairo-1.0-0 libstdc++6 libx11-6 libx11-xcb1 libxcb1 libxcomposite1 libxcursor1 libxdamage1 libxext6 libxfixes3 libxi6 libxrandr2 libxrender1 libxss1 libxtst6 ca-certificates fonts-liberation libappindicator1 libnss3 lsb-release xdg-utils wget xvfb x11vnc x11-xkb-utils xfonts-100dpi xfonts-75dpi xfonts-scalable xfonts-cyrillic x11-apps npm
```

4. Running in non headless mode

```
xvfb-run --server-args="-screen 0 1024x768x24" node app.mjs
```

This guide has not been tested as a launch script yet but these are some of the scripts I have used to run puppeteer on a server which I copy paste from my notion. I just wanted to keep them on github instead for the ease of sharing with others.

I will test this as a server creation script next.
