---
title: GitHub-bidragsarbetsflöde för mindre eller sporadiska ändringar
description: Den här artikeln visar dig hur du använder det "mindre" bidragsarbetsflödet för att göra bidrag i docs.microsoft.com-artiklar.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 10/06/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 8bde44d502e1942b0870df9dd546a97705c2bb4f
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2018
---
# <a name="github-contribution-workflow-for-minor-or-infrequent-changes"></a>GitHub-bidragsarbetsflöde för mindre eller sporadiska ändringar

> [!IMPORTANT]
> Alla informationslager som publicerar till docs.microsoft.com har antagit antingen [Microsoft Open Source-uppförandekoden](https://opensource.microsoft.com/codeofconduct/) eller [.NET Foundation-uppförandekoden](https://dotnetfoundation.org/code-of-conduct). Mer information finns i [vanliga frågor och svar om uppförandekoden](https://opensource.microsoft.com/codeofconduct/faq/). Eller kontakta [opencode@microsoft.com](mailto:opencode@microsoft.com), eller [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) med frågor eller funderingar.<br>
>
> Mindre korrigeringar eller förklaringar till dokumentation och kodexempel i offentliga databaser hittar du i [Användningsvillkor för docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Vid nya eller avsevärda förändringar skapas en kommentar i pull-begäran, där du ombeds skicka in ett licensavtal för bidrag online om du inte är anställd inom Microsoft. Du måste fylla i hela online-formuläret innan vi kan acceptera din pull-begäran.

## <a name="overview"></a>Översikt

Det här arbetsflödet är lämpligt om du ska göra mindre eller sporadiska ändringar med hjälp av GitHubs webbaserade Markdown-redigerare. GitHub-redigeraren är begränsad i vad du kan utföra eftersom användargränssnittet inte har stöd för alla Git-åtgärder och redigeringsscenarier. Om du behöver göra stora bidrag eller behöver support för avancerade Git-funktioner (såsom förgreningshantering eller lösning av avancerad kopplingskonflikt), se [arbetsflöde för större eller långvariga ändringar](full-workflow.md).

## <a name="procedure-for-using-the-github-editor-to-propose-your-changes"></a>Procedur för hur du föreslår ändringar med hjälp av GitHub-redigeraren

1. Bläddra till motsvarande GitHub-lagringsplats och Markdown-fil för artikeln. Du kan använda någon av följande metoder:

   - Leta reda på artikeln genom att söka i Markdown-filerna på motsvarande GitHub-lagringsplats.
   - Gå till artikeln på [docs.microsoft.com](https://docs.microsoft.com/) och välj länken **Redigera** uppe till höger på sidan.

     ![Platsen för länken Redigera](./media/light-workflow/contributetogit.png)

2. Välj pennikonen **Redigera filen** så att redigeringsläget aktiveras:

    ![Platsen för pennikonen](./media/light-workflow/editicon.png)

3. Gör dina ändringar med Markdown på fliken **Redigera fil**, och förhandsgranska dina ändringar under fliken **Förhandsgranska ändringar**. Det är ganska enkelt att använda redigeraren, men om du behöver hjälp kan du se följande riktlinjer:

   - [Hur man använder Markdown](how-to-write-use-markdown.md)
   - [Skapa filer på GitHub](https://github.com/blog/1327-creating-files-on-github)
   - [Överföra filer till lagringsplatserna](https://github.com/blog/2105-upload-files-to-your-repositories)

4. Rulla ner längst ner på sidan där du ser något av följande:

   - **Föreslå fil att ändra**: Visas när du endast har läsåtkomst till lagringsplatsen, såsom vid [Redigera filer i en annan användares lagringsplats](https://help.github.com/articles/editing-files-in-another-user-s-repository/). Om så är fallet kommer GitHub att skapa en gren för "korrigering" i din förgrening av lagringsplatsen (och automatiskt skapa en förgrening om det inte finns någon). När du har valt **Föreslå fil att ändra** visas en sida för att **jämföra ändringar** så att du kan kontrollera dina ändringar. Klicka sedan på knappen **Skapa pull-begäran** för att skicka in dina ändringar till kön för pull-begäranden och fortsätt sedan till [nästa avsnitt](#pull-request-processing).

   - **Spara ändringar**: Visas när du har skrivbehörighet till en lagringsplats, såsom vid [redigering av filer på din egen lagringsplats](https://help.github.com/articles/editing-files-in-your-repository/). Om så är fallet får du två alternativ av GitHub för att spara dina ändringar:

     - **Spara direkt till `<branch-name>`-förgreningen**, där `<branch-name>` är namnet på den förgrening som du var på när du valde knappen **Redigera**. Detta applicerar dina ändringar direkt till förgreningen istället för att använda en pull-begäran. Nu är du färdig!

     - **Skapa en ny förgrening för detta genomförande och starta en pull-begäran**, vilket meddelar ett standardnamn för att skapa en ny förgrening. När du har valt **Föreslå fil att ändra** visas en sida för att **jämföra ändringar** så att du kan kontrollera dina ändringar. Klicka sedan på knappen **Skapa pull-begäran** för att skicka in dina ändringar till kön för pull-begäranden och fortsätt sedan till [nästa avsnitt](#pull-request-processing).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Nästa steg

- Fortsätt till Information om skrivning för att ta reda på mer om Markdown och syntax för Markdown-filtillägg med mera.
