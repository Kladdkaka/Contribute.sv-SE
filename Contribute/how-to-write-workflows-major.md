---
title: GitHub-bidragsarbetsflöde för större och långvariga ändringar
description: Den här artikeln visar dig hur du använder det "större" bidragsarbetsflödet för att göra bidrag i docs.microsoft.com-artiklar.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 08/30/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: e26b62923eed22d5b2005b1d84dc4ae240d262b1
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2018
---
# <a name="github-contribution-workflow-for-major-or-long-running-changes"></a>GitHub-bidragsarbetsflöde för större och långvariga ändringar

> [!IMPORTANT]
> Alla informationslager som publicerar till docs.microsoft.com har antagit antingen [Microsoft Open Source-uppförandekoden](https://opensource.microsoft.com/codeofconduct/) eller [.NET Foundation-uppförandekoden](https://dotnetfoundation.org/code-of-conduct). Mer information finns i [vanliga frågor och svar om uppförandekoden](https://opensource.microsoft.com/codeofconduct/faq/). Eller kontakta [opencode@microsoft.com](mailto:opencode@microsoft.com), eller [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) med frågor eller funderingar.<br>
>
> Mindre korrigeringar eller förklaringar till dokumentation och kodexempel i offentliga databaser hittar du i [Användningsvillkor för docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Vid nya eller avsevärda förändringar skapas en kommentar i pull-begäran, där du ombeds skicka in ett licensavtal för bidrag online om du inte är anställd inom Microsoft. Du behöver slutföra online-formuläret innan din pull-begäran kan sammankopplas.

## <a name="overview"></a>Översikt

Det här arbetsflödet är lämpligt för en deltagare som vill göra en större ändring eller som kommer med frekventa bidrag till en lagringsplats. Deltagare med frekventa bidrag har normalt pågående (långvariga) ändringar, som går igenom flera skapande-/validerings-/mellanlagringscykler eller löper under flera dagar, innan pull-begäran avslutas och sammankopplas.

Exempel på dessa typer av bidrag är:

[!INCLUDE[contribute-major-changes-change-definition](includes/contribute-how-to-write-workflows-major-change-definition.md)]

### <a name="terminology"></a>Terminologi

Innan du börjar, låt oss ta en titt på några Git-/GitHub-termer och monikers som används i det här arbetsflödet. Bry dig inte om ifall du inte förstår dem nu. Du behöver bara veta att du kommer att lära dig om dem och kan referera tillbaka till det här avsnittet om du behöver verifiera en definition.

| Namn | Beskrivning |
|-----------|-------------|
|förgrening|Används normalt som ett substantiv då en kopia av en huvudsaklig GitHub-lagringsplats avses. I praktiken är en förgrening bara en annan lagringsplats. Men den är speciell på det sätt att GitHub behåller en koppling tillbaka till huvudlagringsplatsen. Den används ibland som ett verb, som i "Du måste förgrena lagringsplatsen först."|
|fjärrlagringsplats|En namngiven anslutning till en fjärrlagringsplats, såsom "ursprung" eller "uppströms". Git refererar till dessa som fjärrlagringsplatser eftersom de avser en lagringsplats som finns på en annan dator. I det här arbetsflödet är en fjärrlagringsplats alltid en GitHub-lagringsplats.|
|ursprung|Namnet som har tilldelats anslutningen mellan din lokala lagringsplats och den lagringsplats från vilken den klonats. I det här arbetsflödet representerar ursprung anslutningen till din förgrening. Det används ibland som en moniker för själva ursprungslagringsplatsen, som vid "Kom ihåg att push-överföra dina ändringar till ursprunget".|
|uppströms|Precis som ursprungsfjärrlagringsplatsen är uppströms en namngiven anslutning till en annan lagringsplats. I det här arbetsflödet representerar uppströms anslutningen mellan din lokala lagringsplats och huvudlagringsplatsen från vilken förgreningen skapades. Den används ibland som en moniker för själva uppströmslagringsplatsen, som vid "Kom ihåg att hämta ändringarna från uppströms".|

## <a name="workflow"></a>Arbetsflöde

>[!IMPORTANT]
> Du måste slutföra stegen i [Installationsavsnittet](get-started-setup-github.md) om du inte redan gjort det. Det här avsnittet går igenom installationen av ditt GitHub-konto, installerar Git Bash och en Markdown-redigerare, skapar en förgrening och ställer in din lokala lagringsplats. Om du inte känner till Git- och GitHub-koncept som lagringsplats eller gren bör du först läsa [Information om Git och GitHub](git-github-fundamentals.md).

I det här arbetsflödet flödar ändringar i en repetitiv cykel. Med start från din enhets lokala lagringsplats flödar de tillbaka upp till din GitHub-gren till GitHub-huvudlagringsplatsen och tillbaka ner lokalt igen då du inför ändringar från andra deltagare.

### <a name="use-github-flow"></a>Använd GitHub-flödet

Såsom anges i [Information om Git och GitHub](git-github-fundamentals.md#git) innehåller en Git-lagringsplats en huvudgren samt eventuella ytterligare grenar för pågående arbete som inte har integrerats i huvudgrenen. När du introducerar en uppsättning logiskt relaterade ändringar är bästa praxis att skapa en *arbetsgren* för att hantera dina ändringar genom arbetsflödet. Vi refererar här till det som en arbetsgren eftersom det är ett arbetsutrymme dit ändringar itereras/förfinas tills de kan integreras tillbaka in till huvudgrenen.

Genom att isolera relaterade ändringar till en specifik gren kan du kontrollera och introducera dessa ändringar oberoende och rikta in dem på en specifik frisläppningstid i publiceringscykeln. I själva fallet, beroende på vilken typ av arbete du utför, kan du lätt få flera olika arbetsgrenar i din lagringsplats. Det är inte ovanligt att arbeta med flera grenar på samma gång, där var och en representerar ett projekt.

>[!TIP]
>Att göra dina ändringar i huvudgrenen är *inte* en bra idé. Tänk dig att du använt huvudgrenen för att introducera en uppsättning ändringar för en tidsbestämd funktionsutgåva. Du slutför ändringarna och vi väntar på att ge ut dem. Sedan fick du en brådskande begäran om att korrigera något, så du gjorde ändringen i en fil i huvudgrenen och publicerade sedan ändringen. I det här exemplet publicerar du oavsiktligt både korrigeringen *och* ändringarna som du höll för utgivning på ett specifikt datum.

Nu tar vi och skapar en ny arbetsgren i ditt lokala lager för att samla in dina föreslagna ändringar. Varje git-klient skiljer sig åt så kolla i hjälpen för den klient du föredrar. Du får en översikt över processen i GitHub-guiden på [GitHub-flöde](https://guides.github.com/introduction/flow/).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Nästa steg

Klart! Du har gjort ett bidrag i docs.microsoft.com-innehåll!

- Om du vill veta mer om ämnen som Markdown och syntax för Markdown-filtillägg ska du fortsätta till avsnittet om att skriva.
