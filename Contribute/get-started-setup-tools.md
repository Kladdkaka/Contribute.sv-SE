---
title: Installera innehållsredigeringsverktyg
description: Den här artikeln hjälper dig att hämta och installera de klientverktyg du behöver för Git och för att redigera Markdown-filer.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1011c3fc829202a3df134ddc80eb05b8959b7bf6
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469381"
---
# <a name="install-content-authoring-tools"></a>Installera innehållsredigeringsverktyg

Den här artikeln beskriver stegen för att interaktivt installera Git-klientverktyg och Visual Studio Code.
> [!div class="checklist"]
> * Installera [Git för Windows](https://git-scm.com/download/win)
> * Installera [Visual Studio Code](https://code.visualstudio.com/)
> * Installera [Docs-redigeringspaket](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)

>[!IMPORTANT]
> Om du endast gör mindre ändringar i en artikel behöver du *inte* slutföra det här steget utan kan fortsätta direkt till [arbetsflödet för snabba ändringar](index.md#quick-edits-to-existing-documents).
>
> Frekventa deltagare uppmanas att slutföra de här stegen för kunna använda [arbetsflödet för större/långvariga ändringar](how-to-write-workflows-major.md). Även om du har skrivbehörighet i huvudlagringsplatsen, *rekommenderar vi starkt (och den här guiden förutsätter) att du förgrenar och klonar lagringsplatsen* så att du har läs-/skrivbehörigheter för att lagra dina föreslagna ändringar i din förgrening.

## <a name="install-git-client-tools-on-windows"></a>Installera Git-klientverktyg på Windows

 Installera den senaste versionen av [Programvaran Freedom Conservancys Git-klientverktyg](https://git-scm.com/download/). Installationen inkluderar Git-versionens kontrollsystem och Git Bash, kommandoradsappen som du använder för att interagera med din lokala Git-lagringsplats.

Om du föredrar grafiskt användargränssnitt (GUI) framför kommandoradsgränssnitt (CLI), se [Programvaran Freedom Conservancys tillgängliga GUI-klientsida](https://git-scm.com/downloads/guis), [GitHubs GitHub-skrivbord](https://desktop.github.com/) eller [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) för några populära alternativ.

Följ anvisningarna för att installera och konfigurera din valda klient.

I nästa artikel, kommer du att [konfigurera en lokal Git-lagringsplats](get-started-setup-local.md).

   Ytterligare Git-resurser finns här: [Git-terminologi](https://help.github.com/articles/github-glossary) | [Git-grunderna](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Lär dig Git och GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)

## <a name="understand-markdown-editors"></a>Förstå Markdown-redigerare

Markdown är ett lättviktigt märkspråk som är både enkelt att läsa och lätt att lära sig. Därför har det snabbt blivit en branschstandard. För att skriva artiklar i Markdown rekommenderar vi att du först hämtar och installerar en Markdown-redigerare.  [Visual Studio Code](https://code.visualstudio.com/) är det mest populära verktyget för att redigera Markdown hos Microsoft. [Atom](https://atom.io) är ett annat populärt verktyg för att redigera Markdown.

Markdown-texten sparas i filer med filnamnstillägget .md.

Mer information om hur du skriver med Markdown, inklusive grunderna i Markdown och funktioner som stöds av OPS-anpassade Markdown-tillägg, finns senare i artikeln [Hur man använder Markdown](how-to-write-use-markdown.md).

## <a name="visual-studio-code"></a>Visual Studio Code

[Visual Studio Code](https://code.visualstudio.com/), även kallat VS Code, är en lättviktsredigerare som fungerar på Windows, Linux och Mac. Den inkluderar git-integrering och stöd för tillägg.

Ladda ned och installera [VS Code](https://code.visualstudio.com/). Hemsidan för VS Code borde identifiera ditt operativsystem.

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> Kör kommandot `code .` i kommandoraden eller bash-kommandon för att starta VS Code och öppna den aktuella mappen. Om den aktuella mappen är en del av en lokal git-lagringsplats, visas github-integreringen automatiskt i Visual Studio Code.

## <a name="docs-authoring-pack"></a>Docs-redigeringspaket
Installera Docs-redigeringspaket för Visual Studio Code. Den här uppsättningen av tillägg innefattar grundläggande redigeringshjälp när du skriver Markdown och en förhandsgranskningsfunktion, så att du kan se hur Markdown ser ut i stilen för webbplatsen docs.microsoft.com.

   Besök [marknadsplatssidan](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) och välj **Installera** eller sök efter `docsmsft.docs-authoring-pack` i listan över tillägg i VS Code-fönstret. 

   Docs-redigeringspaketet blir tillgängligt genom att trycka på Alt+M i VS Code. Verktygsfältet är som standard dolt men kan visas. Redigera VS Code-inställningarna (Ctrl+komma) och lägg till användarinställning `"markdown.showToolbar": true` för att visa verktygsfältet.

   Du hittar mer information på sidan [Docs-redigeringspaket](how-to-write-docs-auth-pack.md).


## <a name="next-steps"></a>Nästa steg

Nu är du redo att [konfigurera en lokal Git-lagringsplats](get-started-setup-local.md).
