---
title: Microsoft Docs deltagarguide – översikt
description: Den här guiden beskriver hur du kan bidra till Microsofts dokumentationswebbplats docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 04/17/2018
ms.openlocfilehash: 94fad6f4b2faeefff687eb57cd2de8a0fb5bbbf3
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308903"
---
# <a name="microsoft-docs-contributor-guide-overview"></a>Microsoft Docs deltagarguide – översikt

Välkommen till deltagarguiden för [docs.microsoft.com](https://docs.microsoft.com) (Docs)!

Flera av våra dokumentuppsättningar är öppen källa, med GitHub som värd. Fler och fler team hos Microsoft anammar den här modellen hela tiden. Till och med dokumentuppsättningar som inte är helt öppen källa har offentliga lagringsplatser där du är inbjuden att göra pull-begäranden. Detta strömlinjeformar och förbättrar kommunikationen mellan produktingenjörer, innehållsteam och våra kunder. Att arbeta offentligt ger flera fördelar:

- Lagringsplatser med öppen källkod offentligt för att få feedback på vilka dokument som behövs mest.
- Offentlig granskning av lagringsplatser med öppen källkod för att publicera det mest hjälpfulla innehållet för din första utgåva.
- Offentlig uppdatering av lagringsplatser med öppen källkod för att göra det enklare att hela tiden förbättra innehållet.

Användarupplevelsen på [docs.microsoft.com](https://docs.microsoft.com) integrerar [GitHub](https://github.com)-arbetsflödet direkt för att göra det ännu enklare. Börja med att [redigera det dokument du visar](#quick-edits-to-existing-documents). Hjälp till genom att [granska nya ämnen](#review-open-prs) eller [skapa kvalitetsärenden](#create-quality-issues).

> [!IMPORTANT]
> Alla informationslager som publicerar till docs.microsoft.com har antagit [Microsoft Open Source-uppförandekoden](https://opensource.microsoft.com/codeofconduct/) eller [.NET Foundation-uppförandekoden](https://dotnetfoundation.org/code-of-conduct). Mer information finns i [vanliga frågor och svar om uppförandekoden](https://opensource.microsoft.com/codeofconduct/faq/). Eller kontakta [opencode@microsoft.com](mailto:opencode@microsoft.com), eller [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) med frågor eller funderingar.<br>
>
> Mindre korrigeringar eller förklaringar till dokumentation och kodexempel i offentliga databaser hittar du i [Användningsvillkor för docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Vid nya eller avsevärda förändringar skapas en kommentar i pull-begäran, där du ombes skicka in ett licensavtal för bidrag online om du inte är anställd inom Microsoft. Du måste fylla i hela online-formuläret innan vi kan granska eller acceptera din pull-begäran.

## <a name="quick-edits-to-existing-documents"></a>Snabbredigeringar till existerande dokument

Snabbredigeringar strömlinjeformar processen med att rapportera och korrigera små fel och utelämningar i dokumenten. Trots att vi gör vårt yttersta kan små grammatik- och stavfel hitta sig in bland våra publicerade dokument. Då du kan skapa ärenden för att rapportera misstag. Det är snabbare och enklare att skapa en pull-begäran för att lösa problemet. Nästan alla artiklar har en redigeringsknapp såsom visas i följande figur. Klicka på knappen **Redigera** (eller motsvarande lokalisering) för att komma till källfilen på GitHub.

![Platsen för länken Redigera](./media/index/edit-article.png)

Klicka sedan på pennikonen som visas i följande figur för att redigera artikeln.

> [!NOTE]
> Om pennikonen är nedtonad behöver du logga in på ditt GitHub-konto eller skapa ett nytt konto. Gör dina ändringar i webbredigeraren. Du kan klicka på fliken **Förhandsgranska ändringar** för att kontrollera formateringen på din ändring.

![Platsen för pennikonen](./media/index/editicon.png)

Då du har gjort ändringarna rullar du längst ner på sidan. Ange titel och beskrivning för din pull-begäran och klicka på **Föreslå filändring** såsom visas i följande figur:

![föreslå din ändring](./media/index/submit-pull-request.png)

Nu när du har gjort en föreslagen ändring måste du be ägaren av lagringsplatsen att ”dra” dina ändringar in i lagringsplatsen. Detta görs med någonting som kallas för ”pull-begäran”. När du klickat på **Föreslå filändring** i figuren ovan ska du ha blivit tagen till en ny sida som ser ut som följande bild:

![skapa en pull-begäran](media/index/create-pull-request.png)

Klicka på **Skapa pull-begäran**, ange en titel (och, valfritt, en beskrivning) för pull-begäran och klicka sedan igen på **Skapa pull-begäran**.

Klart! Medlemmar i innehållsteamet kommer att granska och slå samman din pull-begäran. Du kan få viss feedback som begär ändringar om du gjort större ändringar.

Användargränssnittet för GitHub-redigering svarar på dina tillstånd på lagringsplatsen. Följande bilder är korrekta för deltagare som inte har skrivbehörigheter till mållagringsplatsen. GitHub skapar automatiskt en förgrening för mållagringsplatsen i ditt konto. Om du har skrivåtkomst till mållagringsplatsen skapar GitHub en ny gren i mållagringsplatsen. Grennamnet har formatet **\<GitHubId\>-patch-n** och använder ditt GitHub-ID och en numerisk identifierare för korrigeringsgrenen.

Vi använder pull-begäranden för alla ändringar, även för deltagare som har skrivåtkomst. De flesta lagringsplatser har `master`-grenen skyddad så att uppdateringar måste skickas som pull-begäranden.

Redigeringsupplevelsen i webbläsaren är bäst för mindre eller inte ofta förekommande ändringar. Om du gör stora bidrag eller använder avancerade Git-funktioner (såsom förgreningshantering eller lösning av avancerad kopplingskonflikt), behöver du [förgrena lagringsplatsen och arbeta lokalt](how-to-write-workflows-major.md).

> [!NOTE]
> Om det är aktiverat kan du redigera en artikel på **alla språk** och baserat på ändringsstypen händer följande:
> 1. lingvistiska ändringar som godkänns hjälper oss förbättra vår maskinöversättning
> 2. ändringar som gör betydande ändringar av innehållet i en artikel hanteras internt för att skicka in en ändring av samma artikel på engelska, så att den lokaliseras på alla språk, om det godkänns.
> Dina föreslagna förbättringar har inte bara positiv effekt på artiklarna på sitt eget språk, utan för alla tillgängliga språk.

## <a name="review-open-prs"></a>Granska öppna pull-begäranden

Du kan läsa nya ämnen innan de publiceras genom att kontrollera de pull-begäranden som är öppna för tillfället. Granska följande process för [GitHub-flöde](https://guides.github.com/introduction/flow/). Du kan se föreslagna uppdateringar eller nya artiklar i de offentliga lagringsplatserna. Granska dem och lägg till dina kommentarer. Titta på någon av våra dokumentdatabaser och kontrollera de öppna pull-begärandena för områden som intresserar dig. Community-feedback för föreslagna uppdateringar hjälper hela communityn.

## <a name="create-quality-issues"></a>Skapa kvalitetsärenden

Våra dokument är under ständigt pågående arbete. Bra ärenden hjälper oss att fokusera våra ansträngningar med högsta prioritet för communityn. Ju fler detaljer du kan ge, desto hjälpsammare blir ärendet. Berätta för oss vilken information du sökt. Berätta för oss vilka söktermer du använde. Om du inte kommer igång, berätta för oss hur du vill börja att utforska okänd teknik.

Ärenden påbörjar konversationen om vad som behövs. Innehållsteamet kommer att svara på dessa ärenden med idéer om vad vi kan lägga till och be om dina åsikter. Vi kan skapa en skiss och vi kommer att be dig att [granska pull-begärandet](#review-open-prs).

## <a name="get-more-involved"></a>Bli mer involverad

Andra ämnen hjälper dig att komma igång produktivt och bidra till Microsoft Docs. De förklarar hur du arbetar med GitHub-lagringsplatser, Markdown-verktyg och tillägg som används i Microsoft Docs-plattformen.
