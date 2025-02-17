# npm-discord.js

Datum: 09.02.2020

Tutorial 1: [Node.js mit npm](https://www.digitalocean.com/community/tutorials/how-to-use-node-js-modules-with-npm-and-package-json-de)  
Tutorial 2: [How to build a Discord Bot with Node.js](https://www.digitalocean.com/community/tutorials/how-to-build-a-discord-bot-with-node-js)

## Schritte zu 1
1. Privates Repository auf Github anlegen und es mit dieser README.md pushen.
2. Mit ```npm init``` ein Projekt initialisieren. Daraus entsteht die wichtige package.json, in der alle Projektdaten und Abhängigkeiten gemanagt werden. Da Git vorher initialisiert wurde, erkennt npm Git-spezifische Einstellungen automatisch.
3. Die [.gitignore](https://github.com/github/gitignore/blob/master/Node.gitignore) für node.js-Projekte von Github hinzufügen, um u.a. zu verhindern, dass die (vielen) Ordner unter node_modules ins Git gelangen.
4. Jetzt kann man mit ```npm install <Modulname>``` npm-Module installieren. Das Modul und die von ihm abhängigen Module werden in den Ordner node_modules runtergeladen. Modulname und Versionsnummer werden in der package.json unter *dependencies* hinterlegt.  
Mit ```npm install <Modulname> --save-dev``` kann man Module, die nur für die Entwicklung benötigt werden, heruntergeladen werden.

```npm install --production``` : Installation ohne devDependencies  
```npm install <Modulname> -g``` : Globale Installation, z.B. für Node-CLI-Tools  
```npm ls --depth 0``` : Installierte Module ohne Abhängigkeiten auflisten  
```npm outdated``` : Module auflisten, die geupdatet werden können  
```npm up <Modulname>```: Einzelne Module updaten  
```npm un <Modulname>```: Einzelne Module deinstallieren

## Schritte zu 2
1. Im [Discord Developers Portal](https://discord.com/developers/applications) eine App erstellen > Bot erstellen > OAuth2-Link erstellen > Bot per Invite-Link zum eigenen Discord-Server hinzufügen.
2. Projekt per ```npm init``` erstellen.
3. Discord.js mit ```npm install discord.js``` einbinden. Peer dependencies kann man vernachlässigen - das sind alles optionale Features.
4. Entlang des Tutorials coden.

### Interessantes Code-Snippet:
```javascript
else if (command === "sum") {
    const numArgs = args.map(x => parseFloat(x));
    const sum = numArgs.reduce((counter, x) => counter += x);
    message.reply(`The sum of all the arguments is ${sum}!`);
}
```