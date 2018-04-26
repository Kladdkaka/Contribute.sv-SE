---
title: Installera innehållsredigeringsverktyg
description: Den här artikeln hjälper dig att hämta och installera de klientverktyg du behöver för Git och för att redigera Markdown-filer.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 01/04/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 62c4b234f23b470ffea33cacdfc469fbd7e526bd
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2018
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="20326-103">Installera innehållsredigeringsverktyg</span><span class="sxs-lookup"><span data-stu-id="20326-103">Install content authoring tools</span></span>

<span data-ttu-id="20326-104">Den här artikeln beskriver stegen för att interaktivt installera Git-klientverktyg och Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="20326-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="20326-105">Installera [Git för Windows](https://git-scm.com/download/win)</span><span class="sxs-lookup"><span data-stu-id="20326-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="20326-106">Installera [Visual Studio Code](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="20326-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="20326-107">Om du endast gör mindre ändringar i en artikel behöver du *inte* slutföra det här steget utan kan fortsätta direkt till [arbetsflödet för mindre/sporadiska ändringar](light-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="20326-107">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [minor/infrequent changes workflow](light-workflow.md).</span></span>
>
> <span data-ttu-id="20326-108">Frekventa deltagare uppmanas att slutföra de här stegen för kunna använda [arbetsflödet för större/långvariga ändringar](full-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="20326-108">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](full-workflow.md).</span></span> <span data-ttu-id="20326-109">Även om du har skrivbehörighet i huvudlagringsplatsen, *rekommenderar vi starkt (och den här guiden förutsätter) att du förgrenar och klonar lagringsplatsen* så att du har läs-/skrivbehörigheter för att lagra dina föreslagna ändringar i din förgrening.</span><span class="sxs-lookup"><span data-stu-id="20326-109">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="20326-110">Installera Git-klientverktyg på Windows</span><span class="sxs-lookup"><span data-stu-id="20326-110">Install Git client tools on Windows</span></span>

 <span data-ttu-id="20326-111">Installera den senaste versionen av [Programvaran Freedom Conservancys Git-klientverktyg](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="20326-111">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="20326-112">Installationen inkluderar Git-versionens kontrollsystem och Git Bash, kommandoradsappen som du använder för att interagera med din lokala Git-lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="20326-112">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="20326-113">Om du föredrar grafiskt användargränssnitt (GUI) framför kommandoradsgränssnitt (CLI), se [Programvaran Freedom Conservancys tillgängliga GUI-klientsida](https://git-scm.com/downloads/guis), [GitHubs GitHub-skrivbord](https://desktop.github.com/) eller [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) för några populära alternativ.</span><span class="sxs-lookup"><span data-stu-id="20326-113">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="20326-114">Följ anvisningarna för att installera och konfigurera din valda klient.</span><span class="sxs-lookup"><span data-stu-id="20326-114">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="20326-115">I nästa artikel, kommer du att [konfigurera en lokal Git-lagringsplats](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="20326-115">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="20326-116">Ytterligare Git-resurser finns här: [Git-terminologi](https://help.github.com/articles/github-glossary) | [Git-grunderna](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Lär dig Git och GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span><span class="sxs-lookup"><span data-stu-id="20326-116">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="20326-117">Förstå Markdown-redigerare</span><span class="sxs-lookup"><span data-stu-id="20326-117">Understand Markdown editors</span></span>

<span data-ttu-id="20326-118">Markdown är ett lättviktigt märkspråk som är både enkelt att läsa och lätt att lära sig.</span><span class="sxs-lookup"><span data-stu-id="20326-118">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="20326-119">Därför har det snabbt blivit en branschstandard.</span><span class="sxs-lookup"><span data-stu-id="20326-119">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="20326-120">För att skriva artiklar i Markdown rekommenderar vi att du först hämtar och installerar en Markdown-redigerare.</span><span class="sxs-lookup"><span data-stu-id="20326-120">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="20326-121">[Visual Studio Code](https://code.visualstudio.com/) är det mest populära verktyget för att redigera Markdown hos Microsoft.</span><span class="sxs-lookup"><span data-stu-id="20326-121">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="20326-122">[Atom](https://atom.io) är ett annat populärt verktyg för att redigera Markdown.</span><span class="sxs-lookup"><span data-stu-id="20326-122">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="20326-123">Markdown-texten sparas i filer med filnamnstillägget .md.</span><span class="sxs-lookup"><span data-stu-id="20326-123">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="20326-124">Mer information om hur du skriver med Markdown, inklusive grunderna i Markdown och funktioner som stöds av OPS-anpassade Markdown-tillägg, finns senare i artikeln [Hur man använder Markdown](how-to-write-use-markdown.md).</span><span class="sxs-lookup"><span data-stu-id="20326-124">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="20326-125">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="20326-125">Visual Studio Code</span></span>

<span data-ttu-id="20326-126">[Visual Studio Code](https://code.visualstudio.com/), även kallat VS Code, är en lättviktsredigerare som fungerar på Windows, Linux och Mac.</span><span class="sxs-lookup"><span data-stu-id="20326-126">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="20326-127">Den inkluderar git-integrering och stöd för tillägg.</span><span class="sxs-lookup"><span data-stu-id="20326-127">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="20326-128">Ladda ned och installera [VS Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="20326-128">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="20326-129">Hemsidan för VS Code borde identifiera ditt operativsystem.</span><span class="sxs-lookup"><span data-stu-id="20326-129">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="20326-130">Windows</span><span class="sxs-lookup"><span data-stu-id="20326-130">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="20326-131">Mac</span><span class="sxs-lookup"><span data-stu-id="20326-131">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="20326-132">Linux</span><span class="sxs-lookup"><span data-stu-id="20326-132">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="20326-133">Kör kommandot `code .` i kommandoraden eller bash-kommandon för att starta VS Code och öppna den aktuella mappen.</span><span class="sxs-lookup"><span data-stu-id="20326-133">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="20326-134">Om den aktuella mappen är en del av en lokal git-lagringsplats, visas github-integreringen automatiskt i Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="20326-134">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="next-steps"></a><span data-ttu-id="20326-135">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="20326-135">Next steps</span></span>

<span data-ttu-id="20326-136">Nu är du redo att [konfigurera en lokal Git-lagringsplats](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="20326-136">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
