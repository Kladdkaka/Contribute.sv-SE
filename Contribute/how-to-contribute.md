---
title: Hur du kan bidra till docs.microsoft.com
description: Den här artikeln beskriver de olika sätt på vilka du kan bidra med innehåll till docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 01/17/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: bc6f9c314eda5f0d950da049374a7a157f16782a
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-contribute-to-docsmicrosoftcom"></a>Hur du kan bidra till docs.microsoft.com

Det finns flera sätt på vilka du kan förbättra det innehåll som utgör [docs.microsoft.com](https://docs.microsoft.com):

- Du kan [skapa ärenden](#create-issues) för att rekommendera nya artiklar eller förbättra befintliga artiklar.
- Du kan [snabbredigera](#quick-edits) artiklar genom att göra mindre ändringar i GitHub-onlineredigeraren.
- Du kan [granska utkast till nya artiklar](#review-new-articles) så att kvalitet och teknisk noggrannhet garanteras.
- Du kan [skapa nya artiklar](#create-new-articles) om ämnen där du vill bidra till att förbättra innehållet.
- Du kan [uppdatera](#update-samples) eller [skapa](#create-samples) exempel som ger förbättrade kodexempel eller förtydligar viktiga begrepp.

Den här artikeln innehåller information om de sätt på vilka du kan bidra till att var och en av dessa uppgifter utförs. Här finns också länkar till mer information om var och en av dessa aktiviteter.

Våra offentliga databaser finns på [GitHub](https://wwww.GitHub.com).  Du måste skapa ett konto på GitHub för att kunna använda våra dokumentationsdatabaser.

Du behöver också en textredigerare för att kunna uppdatera dokumenten. Vi rekommenderar [Visual Studio Code](https://www.visualstudio.com/code). Du bör ha en grundläggande förståelse av [Markdown](https://daringfireball.net/projects/markdown/syntax)-syntax.

Om du lägger till eller ändrar exempel behöver du en utvecklingsmiljö. Vi rekommenderar [Visual Studio](https://www.visualstudio.com) på PC eller Mac, eller [Visual Studio Code](https://www.visualstudio.com/code) på alla plattformar.

## <a name="create-issues"></a>Skapa ärenden

Om något saknas eller om det förekommer felaktigheter i en artikel, kan du skapa ett ärende. Det enklaste sättet du hittar rätt plats på är genom att klicka på knappen Redigera i din webbläsare, vilket leder dig till artikelns källa i rätt offentliga GitHub-databas. Där kan du hämta artikelkällans webbadress från adressfältet. Skapa ett nytt ärende avseende artikeln genom att klicka på Skapa ärende.

> [!NOTE]
> Om du hittar fel som du kan åtgärda med små ändringar, t.ex. stav- eller grammatikfel så kan du bespara både dig och oss tid genom att [skicka korrigeringen](#quick-edits) genom att redigera källan med hjälp av webbläsaren.

De flesta av våra offentliga databaser innehåller mallar för nya ärenden som förser dig med den information du behöver för att kunna åtgärda felet.

Du kan också skapa nya ärenden när du inte hittar den information du behöver. Processen är densamma: skapa ett nytt ärende på någon av de offentliga dokumentdatabaserna. Berätta för oss vad du sökte, vad du ville göra och varför de artiklar du hittade inte hjälpte dig så som du hade förväntat dig.

## <a name="review-new-articles"></a>Granska nya artiklar

Om du arbetar med ny programvara, eventuellt CTP eller beta, så är vi förmodligen i färd med att skapa dokumenten samtidigt som du utforskar tekniken. Du kan hitta de aktiva dokumenten i våra offentliga databaser. Om du har några kommentarer kan du hjälpa oss att förbättra dokumenten innan de släpps.

Nya artiklar granskas offentligt med hjälp av [GitHub](https://guides.github.com/introduction/flow/)-flödesprocessen. Titta på någon av våra dokumentdatabaser och kontrollera de öppna pullförfrågningarna. Vi välkomnar kommentarer och granskningar av alla öppna pullförfrågningar. Det hjälper oss att publicera bättre innehåll redan i första versionen, i stället för att vänta på feedback tills vi gått live.

Vi försöker hitta olika sätt att förbättra vår tekniska noggrannhet på, tydligare beskrivningar och grammatisk korrekthet.

## <a name="quick-edits"></a>Snabbredigering

Snabbredigering används för att göra små korrigeringar med den webbläsarbaserade redigeraren. Om du hittar små stavnings- eller grammatikfel eller felaktigt namngivna API:er kan du låta bli att skapa ett ärende genom att redigera och skicka en pullförfrågan.

Klicka på knappen Redigera (vanligtvis längst upp till höger på sidan) i artikeln, gör ändringarna och klicka på Skicka pullförfrågan längst ned på sidan. Vi granskar pullförfrågan och sammanfogar den i vår dagliga granskning av pullförfrågningar.

## <a name="create-new-articles"></a>Skapa nya artiklar

Om det finns några begrepp som du är särskilt intresserad av, och som du vill förklara för andra, så kan du skapa artiklar och skicka en pullförfrågan.

Det tar tid att skapa nya artiklar och vi uppskattar den tid du lägger ned på dina bidrag. Vi vill vara med tidigt i processen så att vi kan se att du följa våra riktlinjer och format redan från början. Vi rekommenderar följande åtgärder:

1. [Skapa ett ärende](#create-issues) som beskriver vad som saknas och hur du vill åtgärda detta.
1. Kommentera problemet, berätta för oss om du vill arbeta med det och föreslå en disposition och ett utkast för artikeln.
1. Vi återkommer med förslag. Dessa kan innehålla länkar till relaterade artiklar, förslag på exempel eller förslag på hur artikeln struktureras.
1. När vi är överens om upplägget, så gå till databasen och börja arbeta.
1. Öppna en pullförfrågan tidigt i processen med [WIP] i början av titeln.
1. En av kärndeltagarna ger dig inledande feedback.
1. Fortsätt att skriva, @-mention den person som granskade det första utkast när du är redo för mer feedback.
1. Ta bort [Pågående arbete] när du är klar för den slutliga granskningen.
1. Besvara feedbacken
1. Kärndeltagarna sammanfogar din pullförfrågan.

Det finns ett par saker i listan som det kan vara värt att säga mer om. Vanligtvis granskar vi innehållet så tidigt som möjligt genom att följa [GitHub](https://guides.github.com/introduction/flow/)-flödesprocessen. På så sätt kan vi komma överens om var artikeln ska placeras i innehållsförteckningen, vad läsaren ska få ut av den nya artikeln och hur omfattande eventuella exempel ska vara. Vi kan göra eventuella korrigeringar på ett tidigt stadium, innan du har hunnit lägga ned alltför mycket tid på skrivandet.

## <a name="update-samples"></a>Uppdatera exempel

Vissa exempel har skrivits för äldre versioner med hjälp av metoder som inte längre rekommenderas. Du vill kanske hjälpa oss att uppdatera dessa exempel. Eller så kanske en enkel ändring av variabelnamnet kan öka tydligheten för en förklaring.

Den exempelkod som visas med varje artikel är en del av program som byggts och ofta testats i våra CI-system.

Om du vill göra mindre uppdateringar söker du efter källan i rätt databas, redigerar koden i webbläsaren och skicka en pullförfrågan. Vårt CI-system slutför ändringarna och vi kombinerar pullförfrågan när den är klar.

När det gäller större ändringar delar du databasen och gör ändringarna i din favoritutvecklingsmiljö. Se till att lägga till vissa tester som säkerställer att ändringarna fungerar som du har avsett. Skicka en pullförfrågan och vi granskar den.

Följ gällande kodkonventioner för all kod som du redigerar. Kodningsstandarderna för våra exempellagringsplatser speglar sina respektive produktteam. Sök efter anvisningar för respektive databas.

> [!NOTE]
> Vi arbetar med att följa dessa riktlinjer själva. Några av exemplen skrevs innan våra aktuella standarder trädde i kraft och har ännu inte uppdaterats. Vi arbetar mot ett mål som innebär att all exempelkod ska visas utifrån fungerande och testade exempel.

## <a name="create-samples"></a>Skapa exempel

Du kan även skapa nya exempel som förklarar begrepp eller scenarier. Alla exempel måste åtföljas av en artikel som förklarar nyckelinformationen i exemplet.

Om ditt nya exempel kompletterar en befintlig artikel, så lägg till en referens till exemplet i artikeln. Om inte, så arbeta tillsammans med oss med att [skriva den artikel](#create-new-articles) som medföljer exemplet.

I samtliga fall följer vår exempelkod de kodkonventioner som används av relaterade produktgrupper. Ett undantag är att vi för tydlighetens skull sannolikt använder explicit skrivna variabler istället för implicit skrivna (deklarerade med `var`) när dessa deklarationerna ingår i artikeln.

Följ den exempelprocess som beskrivs i det tidigare avsnittet om [nya artiklar](#create-new-articles), så att vi kan granska koden tidigt i utvecklingsprocessen.
