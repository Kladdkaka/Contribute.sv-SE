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
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/22/2018
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="f2a21-103">Installera innehållsredigeringsverktyg</span><span class="sxs-lookup"><span data-stu-id="f2a21-103">Install content authoring tools</span></span>

<span data-ttu-id="f2a21-104">Den här artikeln beskriver stegen för att interaktivt installera Git-klientverktyg och Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f2a21-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="f2a21-105">Installera [Git för Windows](https://git-scm.com/download/win)</span><span class="sxs-lookup"><span data-stu-id="f2a21-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="f2a21-106">Installera [Visual Studio Code](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="f2a21-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>
> * <span data-ttu-id="f2a21-107">Installera [Docs-redigeringspaket](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span><span class="sxs-lookup"><span data-stu-id="f2a21-107">Install [Docs Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="f2a21-108">Om du endast gör mindre ändringar i en artikel behöver du *inte* slutföra det här steget utan kan fortsätta direkt till [arbetsflödet för snabba ändringar](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="f2a21-108">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>
> <span data-ttu-id="f2a21-109">Frekventa deltagare uppmanas att slutföra de här stegen för kunna använda [arbetsflödet för större/långvariga ändringar](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="f2a21-109">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](how-to-write-workflows-major.md).</span></span> <span data-ttu-id="f2a21-110">Även om du har skrivbehörighet i huvudlagringsplatsen, *rekommenderar vi starkt (och den här guiden förutsätter) att du förgrenar och klonar lagringsplatsen* så att du har läs-/skrivbehörigheter för att lagra dina föreslagna ändringar i din förgrening.</span><span class="sxs-lookup"><span data-stu-id="f2a21-110">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="f2a21-111">Installera Git-klientverktyg på Windows</span><span class="sxs-lookup"><span data-stu-id="f2a21-111">Install Git client tools on Windows</span></span>

 <span data-ttu-id="f2a21-112">Installera den senaste versionen av [Programvaran Freedom Conservancys Git-klientverktyg](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="f2a21-112">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="f2a21-113">Installationen inkluderar Git-versionens kontrollsystem och Git Bash, kommandoradsappen som du använder för att interagera med din lokala Git-lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="f2a21-113">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="f2a21-114">Om du föredrar grafiskt användargränssnitt (GUI) framför kommandoradsgränssnitt (CLI), se [Programvaran Freedom Conservancys tillgängliga GUI-klientsida](https://git-scm.com/downloads/guis), [GitHubs GitHub-skrivbord](https://desktop.github.com/) eller [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) för några populära alternativ.</span><span class="sxs-lookup"><span data-stu-id="f2a21-114">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="f2a21-115">Följ anvisningarna för att installera och konfigurera din valda klient.</span><span class="sxs-lookup"><span data-stu-id="f2a21-115">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="f2a21-116">I nästa artikel, kommer du att [konfigurera en lokal Git-lagringsplats](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="f2a21-116">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="f2a21-117">Ytterligare Git-resurser finns här: [Git-terminologi](https://help.github.com/articles/github-glossary) | [Git-grunderna](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Lär dig Git och GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span><span class="sxs-lookup"><span data-stu-id="f2a21-117">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="f2a21-118">Förstå Markdown-redigerare</span><span class="sxs-lookup"><span data-stu-id="f2a21-118">Understand Markdown editors</span></span>

<span data-ttu-id="f2a21-119">Markdown är ett lättviktigt märkspråk som är både enkelt att läsa och lätt att lära sig.</span><span class="sxs-lookup"><span data-stu-id="f2a21-119">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="f2a21-120">Därför har det snabbt blivit en branschstandard.</span><span class="sxs-lookup"><span data-stu-id="f2a21-120">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="f2a21-121">För att skriva artiklar i Markdown rekommenderar vi att du först hämtar och installerar en Markdown-redigerare.</span><span class="sxs-lookup"><span data-stu-id="f2a21-121">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="f2a21-122">[Visual Studio Code](https://code.visualstudio.com/) är det mest populära verktyget för att redigera Markdown hos Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2a21-122">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="f2a21-123">[Atom](https://atom.io) är ett annat populärt verktyg för att redigera Markdown.</span><span class="sxs-lookup"><span data-stu-id="f2a21-123">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="f2a21-124">Markdown-texten sparas i filer med filnamnstillägget .md.</span><span class="sxs-lookup"><span data-stu-id="f2a21-124">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="f2a21-125">Mer information om hur du skriver med Markdown, inklusive grunderna i Markdown och funktioner som stöds av OPS-anpassade Markdown-tillägg, finns senare i artikeln [Hur man använder Markdown](how-to-write-use-markdown.md).</span><span class="sxs-lookup"><span data-stu-id="f2a21-125">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="f2a21-126">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f2a21-126">Visual Studio Code</span></span>

<span data-ttu-id="f2a21-127">[Visual Studio Code](https://code.visualstudio.com/), även kallat VS Code, är en lättviktsredigerare som fungerar på Windows, Linux och Mac.</span><span class="sxs-lookup"><span data-stu-id="f2a21-127">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="f2a21-128">Den inkluderar git-integrering och stöd för tillägg.</span><span class="sxs-lookup"><span data-stu-id="f2a21-128">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="f2a21-129">Ladda ned och installera [VS Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="f2a21-129">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="f2a21-130">Hemsidan för VS Code borde identifiera ditt operativsystem.</span><span class="sxs-lookup"><span data-stu-id="f2a21-130">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="f2a21-131">Windows</span><span class="sxs-lookup"><span data-stu-id="f2a21-131">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="f2a21-132">Mac</span><span class="sxs-lookup"><span data-stu-id="f2a21-132">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="f2a21-133">Linux</span><span class="sxs-lookup"><span data-stu-id="f2a21-133">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="f2a21-134">Kör kommandot `code .` i kommandoraden eller bash-kommandon för att starta VS Code och öppna den aktuella mappen.</span><span class="sxs-lookup"><span data-stu-id="f2a21-134">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="f2a21-135">Om den aktuella mappen är en del av en lokal git-lagringsplats, visas github-integreringen automatiskt i Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f2a21-135">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="docs-authoring-pack"></a><span data-ttu-id="f2a21-136">Docs-redigeringspaket</span><span class="sxs-lookup"><span data-stu-id="f2a21-136">Docs Authoring Pack</span></span>
<span data-ttu-id="f2a21-137">Installera Docs-redigeringspaket för Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f2a21-137">Install the Docs Authoring Pack for Visual Studio Code.</span></span> <span data-ttu-id="f2a21-138">Den här uppsättningen av tillägg innefattar grundläggande redigeringshjälp när du skriver Markdown och en förhandsgranskningsfunktion, så att du kan se hur Markdown ser ut i stilen för webbplatsen docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="f2a21-138">This set of extensions includes basic authoring assistance for help when writing Markdown, and a preview feature, so that you can see what the Markdown looks like in the style of the docs.microsoft.com site.</span></span>

   <span data-ttu-id="f2a21-139">Besök [marknadsplatssidan](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) och välj **Installera** eller sök efter `docsmsft.docs-authoring-pack` i listan över tillägg i VS Code-fönstret.</span><span class="sxs-lookup"><span data-stu-id="f2a21-139">Visit this [marketplace page](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) and select **Install**, or search for `docsmsft.docs-authoring-pack` in your extensions list in the VS Code window.</span></span> 

   <span data-ttu-id="f2a21-140">Docs-redigeringspaketet blir tillgängligt genom att trycka på Alt+M i VS Code.</span><span class="sxs-lookup"><span data-stu-id="f2a21-140">The Docs Authoring Pack is accessible by pressing Alt+M inside of VS Code.</span></span> <span data-ttu-id="f2a21-141">Verktygsfältet är som standard dolt men kan visas.</span><span class="sxs-lookup"><span data-stu-id="f2a21-141">The toolbar is hidden by default but can be shown.</span></span> <span data-ttu-id="f2a21-142">Redigera VS Code-inställningarna (Ctrl+komma) och lägg till användarinställning `"markdown.showToolbar": true` för att visa verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="f2a21-142">Edit the VS Code settings (Control+comma) and adding user setting `"markdown.showToolbar": true` to show the toolbar.</span></span>

   <span data-ttu-id="f2a21-143">Du hittar mer information på sidan [Docs-redigeringspaket](how-to-write-docs-auth-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f2a21-143">For more information, see the [Docs Authoring Pack](how-to-write-docs-auth-pack.md) page.</span></span>


## <a name="next-steps"></a><span data-ttu-id="f2a21-144">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="f2a21-144">Next steps</span></span>

<span data-ttu-id="f2a21-145">Nu är du redo att [konfigurera en lokal Git-lagringsplats](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="f2a21-145">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
