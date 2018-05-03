---
title: Docs-redigeringspaket för VS Code
description: Tilläggspaketet för VS Code underlättar Markdown-redigering för docs.microsoft.com.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.article: contributor-guide
ms.prod: n.a
ms.service: n.a
ms.technology: n.a
ms.openlocfilehash: 5c857deb07e28e1f6744c895a291bf78a6acf1df
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2018
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs-redigeringspaket för VS Code

Docs-redigeringspaketet är en samling med tillägg för VS Code som hjälper till med Markdown-redigering för docs.microsoft.com. Paketet [finns i VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) och innehåller följande tillägg:

- **DocFx:** Ger en Markdown-förhandsgranskning som är specifik för docs.microsoft.com. Mer information finns i [DocFx](https://marketplace.visualstudio.com/items?itemName=ms-docfx.DocFX).
- **markdownlint:** En populär Markdown-linter från David Anson som hjälper till att säkerställa att Markdown följer de bästa metoderna. Mer information finns i [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint).
- **Docs Markdown:** Ger redigeringshjälp för Markdown för docs.microsoft.com-innehåll i Open Publishing System (OPS), inklusive grundläggande Markdown-stöd och stöd för anpassad Markdown-syntax i OPS. Resten av ämnet beskriver Docs Markdown-tillägget.

## <a name="prerequisites-and-assumptions"></a>Förhandskrav och antaganden

För att kunna infoga relativa länkar, bilder och annat inbäddat innehåll på ett korrekt sätt med Docs Markdown-tillägget måste arbetsytan för VS Code omfatta roten för den klonade OPS-lagringsplatsen.

En del syntax som stöds av tillägget, t.ex. aviseringar och kodfragment, är anpassad Markdown för OPS och renderas inte korrekt om de inte publiceras via OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Använda Docs Markdown-tillägget

Om du vill komma åt menyn för Docs Markdown skriver du `ALT+M`. Du kan klicka eller använda uppåt-/nedåtpilarna för att välja den funktion som önskas, eller skriva för att börja filtrera. Tryck sedan på `ENTER` när den funktion du vill ha är markerad på menyn. Följande är tillgängliga:

|Funktion     |Kommando             |Beskrivning           |
|-------------|--------------------|----------------------|
|Fet stil         |`formatBold`        |Formaterar texten i **fet stil**.|
|Kursiv stil       |`formatItalic`      |Formaterar texten i *kursiv stil*.|
|Kod         |`formatCode`        |Om en rad eller mindre är markerad formateras texten som `inline code`.<br><br>Om flera rader är markerade formateras de som ett inhägnat kodblock, vilket gör det möjligt att välja ett programmeringsspråk som stöds av OPS.|
|Avisering        |`insertAlert`       |Infogar Anmärkning, Viktigt, Varning eller Tips.<br><br>Välj Avisering på menyn och välj sedan aviseringstyp. Om du har markerat text tidigare omges den av vald aviseringssyntax. Om ingen text har markerats läggs en ny avisering till med platshållartext.|
|Numrerad lista|`insertNumberedList` |Infogar en ny numrerad lista.<br><br> Om flera rader har markerats blir var och en ett listobjekt. Tänk på att numrerade listor visas i Markdown som endast 1:or, men de renderas på docs.microsoft.com som sekventiella siffror eller, för kapslade listor, bokstäver. Om du vill skapa en kapslad numrerad lista tabbar du i den överordnade listan.|
|Punktlista|`insertBulletedList` |Infogar en ny punktlista.|
|Tabell        |`insertTable`        |Infogar en Markdown-tabellstruktur.<br><br>När du har valt tabellkommandot anger du antalet kolumner och rader med formatet kolumner:rader, t.ex. 3:4. Tänk på att det högsta antalet kolumner du kan ange via detta tillägg är 5, vilket är rekommenderat högsta antal för läsbarhet.|
|Länk         |`selectLinkType`      |Infogar en länk. Följande undermeny visas när du väljer detta kommando.<br><br>`External`: Länk till en webbsida med URI. Måste omfatta "http" eller "https".<br>`Internal`: Infoga en relativ länk till en annan fil i samma lagringsplats. När du har valt det här kommandot skriver du i kommandofönstret för att filtrera filerna efter namn, och väljer sedan den fil som önskas. <br>`Bookmark in this file`: Välj bland en lista med rubriker i aktuell fil för att infoga ett bokmärke med korrekt formatering.<br>`Bookmark in another file`: Filtrera först efter filnamn och välj filen som du vill länka till, och välj sedan lämplig rubrik i den valda filen.|
|Bild        |`insertImage`     |Skriv in alternativ text (krävs för tillgänglighet) och markera den. Anropa sedan detta kommando för att filtrera listan över bildfiler som stöds i lagringsplatsen och välj den som önskas. Om du inte har valt alternativ text när du anropar detta kommando uppmanas du att ange det innan du kan välja en bildfil.|
|Inkludera      |`insertInclude`   |Hitta en fil att bädda in i den aktuella filen.|
|Kodfragment      |`insertSnippet`   |Hitta ett kodfragment i lagringsplatsen att bädda in i den aktuella filen.|
|Video        |`insertVideo`     |Lägg till ett inbäddat videoklipp|
|Förhandsgranskning      |`previewTopic`    |Förhandsgranska det aktiva ämnet i ett fönster sida vid sida med hjälp av DocFX-tillägget.  Om DocFX-tillägget inte är installerat, eller om det är installerat men inaktiverat, kommer ämnet inte att renderas.


## <a name="how-to-assign-keyboard-shortcuts"></a>Tilldela kortkommandon

1. Skriv in `CTRL+K` och sedan `CTRL+S` för att öppna listan med kortkommandon.
1. Sök efter kommandot, t.ex. `formatBold`, som du vill skapa en anpassad tangentkoppling till.
1. Klicka på plustecknet som visas bredvid kommandonamnet när du för muspekaren över raden.
1. När en ny inmatningsruta visas skriver du in det kortkommando som du vill koppla till just det kommandot. Om du till exempel vill använda den vanliga genvägen för fet stil kan du skriva `ctrl+b`.
1. Det kan vara bra att infoga en `when`-sats i tangentkopplingen, så att den inte är tillgänglig i några andra filer än Markdown. Det gör du genom att öppna *keybindings.json* och infoga följande rad under kommandonamnet (tänk på att lägga till ett kommatecken mellan raderna):
   
    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    Den färdiga anpassade tangentkopplingen bör se ut så här i keybindings.json:

    ```json
    // Place your key bindings in this file to overwrite the defaults
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

1. Spara keybindings.json.

Se [Keybindings](https://code.visualstudio.com/docs/getstarted/keybindings) (Tangentkopplingar) i dokumentationen för VS Code om du vill ha mer information.

## <a name="how-to-show-the-legacy-gauntlet-toolbar"></a>Visa det äldre verktygsfältet "Gauntlet"

Tidigare användare av tilläggskoden med namnet "Gauntlet" kommer att se att redigeringsverktygsfältet inte längre visas längst ned i fönstret för VS Code när Docs Markdown-tillägget har installerats. Det beror på att verktygsfältet tog upp stort utrymme i statusfältet för VS Code och inte följde de bästa metoderna för tilläggs-UX, så funktionen har tagits bort i det nya tillägget. Du kan dock välja att visa verktygsfältet genom att uppdatera VS Code-filen settings.json på följande sätt:

1. I VS Code går du till Arkiv -> Inställningar -> Inställningar (`CTRL+Comma`).
1. Välj Användarinställningar för att ändra inställningarna för alla arbetsytor i VS Code, eller Inställningar för arbetsyta om du bara vill ändra dem för den aktuella arbetsytan.
1. I fönstret Standardinställningar letar du reda på Docs Authoring Extension Configuration (Konfiguration av Docs-redigeringstillägg) och väljer pennikonen bredvid önskad inställning. Du uppmanas sedan att välja antingen `true` eller `false`. När du har gjort ett val lägger VS Code automatiskt till värdet i filen settings.json och du uppmanas att uppdatera fönstret för att ändringarna ska börja gälla.

## <a name="known-issues"></a>Kända problem

- [DocFX-förhandsgranskning] MacOS och Linux: DocFX-förhandsgranskningen startas inte korrekt (förhandsgranskningen går som standard till förhandsgranskning för VS Code Markdown för dessa plattformar).
- [DocFx-förhandsgranskning] Alla plattformar: En del syntax, t.ex. xref-länkar (korsreferens) till API:er, renderas inte korrekt i förhandsgranskning. I vissa fall blir det luckor i innehållet.
- [Externa bokmärken] Linux: Fillistan visas men det visas inga rubriker som kan väljas.
- [Inkluderingar] Linux: Fillistan visas men ingen länk läggs till efter att ett val har gjorts.