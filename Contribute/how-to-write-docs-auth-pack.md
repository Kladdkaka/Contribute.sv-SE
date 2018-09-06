---
title: Docs-redigeringspaket för VS Code
description: Den här artikeln beskriver Tilläggspaketet för VS Code för att underlätta Markdown-redigering för docs.microsoft.com.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.openlocfilehash: b9fedce0a73c5c4212ffd0893c745fab56677c8c
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308926"
---
# <a name="docs-authoring-pack-for-vs-code"></a>Docs-redigeringspaket för VS Code

Docs-redigeringspaketet är en samling med tillägg för VS Code som hjälper till med Markdown-redigering för docs.microsoft.com. Paketet [finns i VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) och innehåller följande tillägg:

- [markdownlint:](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) En populär Markdown-linter från David Anson som hjälper till att säkerställa att Markdown följer de bästa metoderna.
- [Stavningskontroll i Code](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): En offline-stavningskontroll från Street Side Software.
- [Docs-förhandsgranskning](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): Använder docs.microsoft.com CSS för mer noggrann Markdown-förhandsgranskning, inklusive anpassad Markdown.
- [Docs Markdown:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) Ger redigeringshjälp för Markdown för docs.microsoft.com-innehåll i Open Publishing System (OPS), inklusive grundläggande Markdown-stöd och stöd för anpassad Markdown-syntax i OPS. Resten av ämnet beskriver Docs Markdown-tillägget.
- [Docs-artikelmallar](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): Låter användare använda Markdown-utkast på nya filer.

## <a name="prerequisites-and-assumptions"></a>Förhandskrav och antaganden

För att kunna infoga relativa länkar, bilder och annat inbäddat innehåll på ett korrekt sätt med Docs Markdown-tillägget måste arbetsytan för VS Code omfatta roten för den klonade Open Publishing System-lagringsplatsen (OPS).

En del syntax som stöds av tillägget, t.ex. aviseringar och kodfragment, är anpassad Markdown för OPS och renderas inte korrekt om de inte publiceras via OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Använda Docs Markdown-tillägget

Om du vill komma åt menyn för Docs Markdown skriver du `ALT+M`. Du kan klicka eller använda uppåt-/nedåtpilarna för att välja den funktion som önskas, eller skriva för att börja filtrera. Tryck sedan på `ENTER` när den funktion du vill ha är markerad på menyn. Följande är tillgängliga:

|Funktion     |Beskrivning           |
|-------------|----------------------|
|Förhandsgranskning      |Förhandsgranska det aktiva ämnet i ett fönster sida vid sida med hjälp av Docs förhandsgranskningstillägg. Alternativet är endast tillgängligt om Docs-förhandsgranskning är installerat.|
|Fet stil         |Formaterar texten i **fet stil**.|
|Kursiv stil       |Formaterar texten i *kursiv stil*.|
|Kod         |Om en rad eller mindre är markerad formateras texten som `inline code`.<br><br>Om flera rader är markerade formateras de som ett inhägnat kodblock, vilket gör det möjligt att välja ett programmeringsspråk som stöds av OPS.|
|Avisering        |Infogar Anmärkning, Viktigt, Varning eller Tips.<br><br>Välj Avisering på menyn och välj sedan aviseringstyp. Om du har markerat text tidigare omges den av vald aviseringssyntax. Om ingen text har markerats läggs en ny avisering till med platshållartext.|
|Numrerad lista|Infogar en ny numrerad lista.<br><br> Om flera rader har markerats blir var och en ett listobjekt. Tänk på att numrerade listor visas i Markdown som endast 1:or, men de renderas på docs.microsoft.com som sekventiella siffror eller, för kapslade listor, bokstäver. Om du vill skapa en kapslad numrerad lista tabbar du i den överordnade listan.|
|Punktlista|Infogar en ny punktlista.|
|Tabell        |Infogar en Markdown-tabellstruktur.<br><br>När du har valt tabellkommandot anger du antalet kolumner och rader med formatet kolumner:rader, t.ex. 3:4. Tänk på att det högsta antalet kolumner du kan ange via detta tillägg är 5, vilket är rekommenderat högsta antal för läsbarhet.|
|Länk till filens lagringsplats|Infogar en relativ länk till en annan fil i den aktuella lagringsplatsen. När du har valt det här kommandot skriver du i kommandofönstret för att filtrera filerna efter namn, och väljer sedan den fil som önskas. Om du har valt text tidigare kommer det att bli länktexten. Annars används målfilens H1 som länktext.|
|Länk till webbsida    |Infogar en länk till en webbsida. Kopiera eller skriv in URI i kommandofönstret efter att detta alternativet valts. `https://` måste anges. Om du har valt text tidigare kommer det att bli länktexten. Annars används URI som länktext.|
|Länk till rubrik     |Länkar till bokmärken i den aktuella filen eller en annan fil i lagringsplatsen.<br>`Bookmark in this file`: Välj bland en lista med rubriker i aktuell fil för att infoga ett bokmärke med korrekt formatering.<br>`Bookmark in another file`: Filtrera först efter filnamn och välj filen som du vill länka till, och välj sedan lämplig rubrik i den valda filen.|
|Bild        |Skriv in alternativ text (krävs för tillgänglighet) och markera den. Anropa sedan detta kommando för att filtrera listan över bildfiler som stöds i lagringsplatsen och välj den som önskas. Om du inte har valt alternativ text när du anropar detta kommando uppmanas du att ange det innan du kan välja en bildfil.|
|Inkludera      |Hitta en fil att bädda in i den aktuella filen.|
|Kodfragment      |Hitta ett kodfragment i lagringsplatsen att bädda in i den aktuella filen.|
|Video        |Lägg till ett inbäddat videoklipp|
|Mall     |Skapa en ny fil och applicera en Markdown-mall. Se [Mallar](#how-to-use-docs-templates) nedan för mer information.|

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

## <a name="how-to-show-the-legacy-toolbar"></a>Visa det äldre verktygsfältet

Användare av den tidigare släppta tilläggsversionen kommer att se att redigeringsverktygsfältet inte längre visas längst ned i fönstret för VS Code när Docs Markdown-tillägget har installerats. Det beror på att verktygsfältet tog upp stort utrymme i statusfältet för VS Code och inte följde de bästa metoderna för tilläggs-UX, så funktionen har tagits bort i det nya tillägget. Du kan dock välja att visa verktygsfältet genom att uppdatera VS Code-filen settings.json på följande sätt:

1. I VS Code går du till Arkiv -> Inställningar -> Inställningar (`CTRL+Comma`).
1. Välj Användarinställningar för att ändra inställningarna för alla arbetsytor i VS Code, eller Inställningar för arbetsyta om du bara vill ändra dem för den aktuella arbetsytan.
1. I fönstret Standardinställningar letar du reda på Docs Authoring Extension Configuration (Konfiguration av Docs-redigeringstillägg) och väljer pennikonen bredvid önskad inställning. Du uppmanas sedan att välja antingen `true` eller `false`. När du har gjort ett val lägger VS Code automatiskt till värdet i filen settings.json och du uppmanas att uppdatera fönstret för att ändringarna ska börja gälla.

## <a name="how-to-use-docs-templates"></a>Så här används Docs-mallar

Tillägget för Docs-artikelmallar låter programmerare i VS Code plocka en Markdown-mall från en central butik och applicera den på en fil. Mallar kan hjälpa till att se till att den metadata som krävs är inkluderad i artiklar, att innehållsstandarder följs och så vidare. Mallar hanteras som Markdown-filer i en offentlig GitHub-lagringsplats.

### <a name="to-apply-a-template-in-vs-code"></a>Applicera en mall i VS Code

1. Om du inte har Docs Markdown-tillägget installerat trycker du på F1 för att öppna kommandopaletten, börjar skriva ”mall” för att filtrera och klickar sedan `Docs: Template`. Om du har Docs Markdown-tillägget installerat kan du antigen använda kommandopaletten eller klicka på `Alt+M` för att ta fram Docs Markdown QuickPick-menyn och sedan välja `Template` i listan.
1. Välj mall i listan som visas.

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>Så här lägger du till ditt GitHub-id och/eller Microsoft-alias till inställningarna i VS Code

Malltillägget stöder tre dynamiska metadatafält: författare, ms.author och ms.date. Det innebär att om en mallskapare använder dessa fält i metadatarubriken för en Markdown-mall kommer de att fyllas i automatiskt i din fil när du tillämpar mallen så som följer:

|Metadata  |Värde|
|----------|---------------|
|författare    |Ditt GitHub-id om det anges i din inställningsfil för VS Code.|
|ms.author |Ditt Microsoft-alias om det anges i din inställningsfil för VS Code. Lämna fältet tomt om du inte är anställd hos Microsoft.|
|ms.date   |Det nuvarande datumet i formatet som stöds av Docs – MM/DD/YYYY. Observera att datumet inte uppdateras automatiskt om du sedan uppdaterar filen. Du måste uppdatera detta manuellt för att indikera artikelns aktualitetsdatum.|

### <a name="to-set-author-github-id-andor-msauthor-microsoft-alias"></a>Så här ställer du in författare (GitHub-id) och/eller ms.author (Microsoft-alias)

1. I VS Code går du till Arkiv -> Inställningar -> Inställningar (`CTRL+Comma`).
1. Välj Användarinställningar för att ändra inställningarna för alla arbetsytor i VS Code, eller Inställningar för arbetsyta om du bara vill ändra dem för den aktuella arbetsytan.
1. Hitta konfiguration av tillägget Docs-artikelmallar i standardinställningar, klicka på pennikonen bredvid inställningen du vill ha och klicka sedan på Ersätt under Inställningar.
1. Panelen användarinställningar öppnas sida-vid-sida med en ny inmatning längst ner.
1. Lägg till ditt GitHub-id eller e-postalias för Microsoft där lämpligt och spara filen.
1. Du kan behöva stänga och starta om VS Code för att ändringarna ska träda i kraft.
1. När du nu applicerar en mall som använder dynamiska fält kommer ditt GitHub-id och/eller Microsoft-alias att fyllas i automatiskt i metadatarubriken.
