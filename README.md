# Uppstart

## Installation

Vi behöver WSL2 för att köra node, eller det gör livet enklare, bättre och snabbare.
Guide till att installera WSL2 finns här: [https://docs.microsoft.com/en-us/windows/wsl/install-win10](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

WSL står för Windows Subsystem for Linux och är en Linux-kärna som körs i Windows. Detta gör att vi kan köra Linux-kommandon i Windows.
Vi kommer att använda Ubuntu som Linux-distribution.

### Installera Ubuntu

1. Öppna Microsoft Store
2. Sök efter Ubuntu
3. Klicka på Ubuntu och Installera
4. Starta Ubuntu
5. Skapa ett användarnamn och lösenord

#### Uppdatera Ubuntu

För att se till att Ubuntu är uppdaterat kör följande kommandon:

```bash
sudo apt update
sudo apt upgrade
```

Sudo är superuser do och används för att köra kommandon som kräver administratörsrättigheter. Apt är ett verktyg för att installera och uppdatera program i Ubuntu.
Så med andra ord kör du typ windows update som datoradministratör.

### Installera Node med NVM

NVM står för Node Version Manager och är ett verktyg för att installera och hantera olika versioner av Node.js.

[Guide](https://learn.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-wsl) för att installera Node.js med NVM.

## Skapa ett nytt projekt

Vi kommer att spara all kod på linux filsystemet som WSL skapat på din dator. 
Starta Ubuntu / WSL eller kör det med [Windows Terminal](https://apps.microsoft.com/detail/9n0dx20hk701?hl=en-US&gl=US).

När du startar detta så är du förhoppningsvis i din hemkatalog. Om inte så kan du komma dit genom att köra:

```bash
cd ~
```

Kontrollera att du är i din hemkatalog genom att köra:

```bash
pwd
```

Det bör står `/home/ditt-användarnamn`.

Nu ska du skapa en `code` mapp där du kan spara alla dina projekt. Detta gör du genom att köra:

```bash
mkdir code
```

Vad tror du att kommandona du hittills kört betyder, `cd`, `pwd`, `mkdir`? Det finns ett system och det är förkortningar.

Nu ska vi skapa ett nytt projekt. Gå in i mappen `code` genom att köra:

```bash
cd code
```

Nu ska du skapa en ny mapp för ditt projekt. Vi kommer att skapa ett projekt som heter `hello-world`. Skapa mappen genom att köra:

```bash
mkdir hello-world
```

Gå in i mappen genom att köra:

```bash
cd hello-world
```

Nu är du i din projektmapp. Här kan du skapa alla filer och mappar som du behöver för ditt projekt.

Om du behöver se vilka filer som finns i mappen kan du köra:

```bash
ls
```

För lite mer information om filerna kan du köra:

```bash
ls -la
```

## Initiera node-projekt

Nu ska vi initiera ett nytt node-projekt. Detta gör vi genom att köra:

```bash
npm init -y
```

Detta kommer att skapa en `package.json` fil i din projektmapp. Denna fil innehåller information om ditt projekt och dess dependencies.
-y flaggan gör så att du inte behöver svara på några frågor när du initierar projektet, du kan testa att köra kommandot utan -y och se vad som händer.

Vill du ha mer information om npm kan du köra:

```bash
npm help
```

package.json filen kommer att se ut ungefär så här:
```json
{
  "name": "hello-world",
  "version": "1.0.0",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "description": "",
}
```

## Git och GitHub

Byt till source control i VS Code och initiera ett nytt git-repo. Lägg till alla filer och gör en commit. Skapa ett nytt repo på GitHub och pusha upp ditt projekt.

För att undvika att ladda upp filer kopplade till node så kan du skapa en `.gitignore` fil i din projektmapp och lägga till `node_modules` i filen.

```bash
echo "node_modules" > .gitignore
```

## Installera Express

Express är ett webbramverk för Node.js. Vi kommer att använda Express för att skapa en enkel webbserver.

Installera Express genom att köra:

```bash
npm install express
```

Vi kommer att skapa din server i en fil som heter `server.js`. Skapa filen genom att köra:

```bash
touch server.js
```

Öppna mappen i VS Code genom att köra:

```bash
code .
```

I server filen så kommer vi att använda oss av ESM (ECMAScript Modules) för att kunna använda modern JavaScript-syntax. 
ESM är en standard för att importera och exportera moduler i JavaScript.

För att det ska fungera behöver vi redigera `package.json` så att node vet om att vi använder oss av ESM.

Lägg till `"type": "module"` i `package.json` filen så att den ser ut så här:

```json
{
  "type": "module",
  "main": "server.js",
}
```

## Testa att det fungerar

Vi kan nu bara testa att köra igång servern. I `server.js` skriv följande kod:

```javascript
console.log('Hello World');
```

Kör servern genom att köra:

```bash
node server.js
```

Om du ser `Hello World` i terminalen så fungerar allt som det ska.





