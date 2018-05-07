---
title: Ställ in Git-lagringsplatsen lokalt
description: Den här artikeln ger vägledning om hur du skapar en lokal Git-lagringsplats och bidrar till dokumentation, inklusive processen för att förgrena och klona.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 01/18/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: f702d0d29ee7dc9c69cb26b79bf6283d91b6b6bc
ms.sourcegitcommit: 3ec397fab57ea582edb03a59609f62d886410ee8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2018
---
# <a name="set-up-git-repository-locally-for-documentation"></a><span data-ttu-id="2e75c-103">Ställ in Git-lagringsplatsen lokalt för dokumentation</span><span class="sxs-lookup"><span data-stu-id="2e75c-103">Set up Git repository locally for documentation</span></span>

<span data-ttu-id="2e75c-104">Den här artikeln beskriver stegen för att ställa in en git-lagringsplats på din lokala dator, i syfte att bidra till Microsoft-dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-104">This article describes the steps to set up a git repository on your local machine, with the intent to contribute to Microsoft documentation.</span></span> <span data-ttu-id="2e75c-105">Deltagare kan använda en lokalt klonad lagringsplats för att lägga till nya artiklar, utföra större ändringar i befintliga artiklar eller ändra bilder.</span><span class="sxs-lookup"><span data-stu-id="2e75c-105">Contributors may use a locally cloned repository to add new articles, do major edits on existing articles, or change artwork.</span></span>

<span data-ttu-id="2e75c-106">Du kan köra de här engångsaktiviteterna för konfiguration för att komma igång och bidra:</span><span class="sxs-lookup"><span data-stu-id="2e75c-106">You run these one-time setup activities to get started contributing:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2e75c-107">Fastställ en lämplig lagringsplats</span><span class="sxs-lookup"><span data-stu-id="2e75c-107">Determine the appropriate repository</span></span>
> * <span data-ttu-id="2e75c-108">Förgrena lagringsplatsen till ditt GitHub-konto</span><span class="sxs-lookup"><span data-stu-id="2e75c-108">Fork the repository to your GitHub account</span></span>
> * <span data-ttu-id="2e75c-109">Välj en lokal mapp för de klonade filerna</span><span class="sxs-lookup"><span data-stu-id="2e75c-109">Choose a local folder for the cloned files</span></span>
> * <span data-ttu-id="2e75c-110">Klona lagringsplatsen till din lokala dator</span><span class="sxs-lookup"><span data-stu-id="2e75c-110">Clone the repository to your local machine</span></span>
> * <span data-ttu-id="2e75c-111">Konfigurera det överordnade fjärrvärdet</span><span class="sxs-lookup"><span data-stu-id="2e75c-111">Configure the upstream remote value</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e75c-112">Om du bara gör mindre ändringar i en artikel behöver du *inte* slutföra stegen i den här artikeln.</span><span class="sxs-lookup"><span data-stu-id="2e75c-112">If you're making only minor changes to an article, you *do not* need to complete the steps in this article.</span></span> <span data-ttu-id="2e75c-113">Du kan fortsätta direkt till [arbetsflödet för snabba ändringar](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="2e75c-113">You can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>

## <a name="overview"></a><span data-ttu-id="2e75c-114">Översikt</span><span class="sxs-lookup"><span data-stu-id="2e75c-114">Overview</span></span>

<span data-ttu-id="2e75c-115">För att bidra till Microsofts dokumentationswebbplats, kan du skapa och redigera Markdown-filer lokalt genom att klona motsvarande dokumentationslager.</span><span class="sxs-lookup"><span data-stu-id="2e75c-115">To contribute to Microsoft's documentation site, you can make and edit Markdown files locally by cloning the corresponding documentation repository.</span></span> <span data-ttu-id="2e75c-116">Microsoft kräver att du förgrenar den lämpliga lagringsplatsen till ditt eget github-konto så att du har läs-/skrivbehörigheter där att lagra dina föreslagna ändringar.</span><span class="sxs-lookup"><span data-stu-id="2e75c-116">Microsoft requires you to fork the appropriate repository into your own github account, so that you have read/write permissions there to store your proposed changes.</span></span> <span data-ttu-id="2e75c-117">Du kan sedan använda pull-begäranden för att slå samman ändringar i den skrivskyddade centrala delade lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-117">Then you use pull requests to merge changes into the read-only central shared repository.</span></span>

![GitHub-triangeln](./media/git-and-github-initial-setup.png)

<span data-ttu-id="2e75c-119">Om du är en ny användare av GitHub kan du titta på följande video som innehåller en översikt över förgrening och kloning:</span><span class="sxs-lookup"><span data-stu-id="2e75c-119">If you're new to GitHub, watch the following video for a conceptual overview of the forking and cloning process:</span></span>

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a><span data-ttu-id="2e75c-120">Fastställ lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="2e75c-120">Determine the repository</span></span>

<span data-ttu-id="2e75c-121">Dokumentation som finns på [docs.microsoft.com](https://docs.microsoft.com) befinner sig i flera olika lagringsplatser på [github.com](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="2e75c-121">Documentation hosted at [docs.microsoft.com](https://docs.microsoft.com) resides in several different repositories at [github.com](https://www.github.com).</span></span>

1. <span data-ttu-id="2e75c-122">Om du är osäker på vilken lagringsplats du ska använda, kan du gå till artikeln på docs.microsoft.com med din webbläsare.</span><span class="sxs-lookup"><span data-stu-id="2e75c-122">If you are unsure of which repository to use, then visit the article on docs.microsoft.com using your web browser.</span></span> <span data-ttu-id="2e75c-123">Välj **Redigera**-länken (pennikonen) i det övre högra hörnet på artikeln.</span><span class="sxs-lookup"><span data-stu-id="2e75c-123">Select the **Edit** link (pencil icon) on the upper right of the article.</span></span>

   ![Klicka på Redigera för att se lagringsplatsen och filplatsen.](media/index/edit-article.png)

2. <span data-ttu-id="2e75c-125">Länken tar dig till github.com-platsen för motsvarande Markdown-fil i lämplig lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="2e75c-125">That link takes you to github.com location for the corresponding Markdown file in the appropriate repository.</span></span> <span data-ttu-id="2e75c-126">Lägg märke till URL:en för att se lagringsplatsens namn.</span><span class="sxs-lookup"><span data-stu-id="2e75c-126">Note the URL to view the repository name.</span></span>

   ![Lägg märke till URL:en för att lagringsplatsen.](media/public-repo.png)

   <span data-ttu-id="2e75c-128">De här populära lagringsplatserna finns till exempel tillgängliga för offentliga bidrag:</span><span class="sxs-lookup"><span data-stu-id="2e75c-128">For example, these popular repositories are available for public contributions:</span></span>
   - <span data-ttu-id="2e75c-129">Azure-dokumentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span><span class="sxs-lookup"><span data-stu-id="2e75c-129">Azure documentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span></span>
   - <span data-ttu-id="2e75c-130">Dokumentation om SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span><span class="sxs-lookup"><span data-stu-id="2e75c-130">SQL Server documentation [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span></span>
   - <span data-ttu-id="2e75c-131">Visual Studio-dokumentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span><span class="sxs-lookup"><span data-stu-id="2e75c-131">Visual Studio documentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span></span>
   - <span data-ttu-id="2e75c-132">.NET-dokumentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span><span class="sxs-lookup"><span data-stu-id="2e75c-132">.NET Documentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span></span>
   - <span data-ttu-id="2e75c-133">Azure .Net SDK-dokumentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span><span class="sxs-lookup"><span data-stu-id="2e75c-133">Azure .Net SDK documentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span></span>

## <a name="fork-the-repository"></a><span data-ttu-id="2e75c-134">Förgrena lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="2e75c-134">Fork the repository</span></span>
<span data-ttu-id="2e75c-135">Använd lämplig lagringsplats för att skapa en förgrening av lagringsplatsen till ditt eget GitHub-konto med hjälp av GitHub-webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-135">Using the appropriate repository, create a fork of the repository into your own GitHub account by using the GitHub website.</span></span>

<span data-ttu-id="2e75c-136">En personlig förgrening krävs eftersom alla huvudsakliga dokumentationslagringsplatser endast ger läsbehörighet, vilket innebär att du inte kan ändra innehåll i lagringsplatsen direkt.</span><span class="sxs-lookup"><span data-stu-id="2e75c-136">A personal fork is required since all main documentation repositories provide read-only access, which means you cannot make changes directly on content in the repositories.</span></span> <span data-ttu-id="2e75c-137">För att utföra ändringar måste du skicka in en [pull-begäran](git-github-fundamentals.md#pull-requests) från förgreningen till huvudlagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-137">To make changes, you must submit a [pull request](git-github-fundamentals.md#pull-requests) from your fork into the main repository.</span></span> <span data-ttu-id="2e75c-138">Den här processen förenklas om du först har en kopia av lagringsplatsen där du har skrivbehörighet.</span><span class="sxs-lookup"><span data-stu-id="2e75c-138">To facilitate this process, you first need your own copy of the repository, in which you have write access.</span></span> <span data-ttu-id="2e75c-139">En GitHub-*förgrening* har denna funktion.</span><span class="sxs-lookup"><span data-stu-id="2e75c-139">A GitHub *fork* serves that purpose.</span></span>

1. <span data-ttu-id="2e75c-140">Gå till huvudlagringsplatsens GitHub-sida och klicka på knappen **Förgrening** längst upp till höger.</span><span class="sxs-lookup"><span data-stu-id="2e75c-140">Go to the main repository's GitHub page and click the **Fork** button on the upper right.</span></span>

   ![Exempel på GitHub-profil](./media/contribute-get-started-setup-local/fork.png)

2. <span data-ttu-id="2e75c-142">Om du uppmanas om detta ska du välja en GitHub-kontoikon som destination för förgreningen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-142">If you are prompted, select your GitHub account tile as the destination where the fork should be created.</span></span> <span data-ttu-id="2e75c-143">Detta skapar en kopia av lagringsplatsen i ditt GitHub-konto, vilket kallas en förgrening.</span><span class="sxs-lookup"><span data-stu-id="2e75c-143">This prompt creates a copy of the repository within your GitHub account, known as a fork.</span></span>

## <a name="choose-a-local-folder"></a><span data-ttu-id="2e75c-144">Välj en lokal mapp</span><span class="sxs-lookup"><span data-stu-id="2e75c-144">Choose a local folder</span></span>
<span data-ttu-id="2e75c-145">Skapa en lokal mapp för att lagra en lokal kopia av lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-145">Make a local folder to hold a copy of the repository locally.</span></span> <span data-ttu-id="2e75c-146">En del lagringsplatser kan vara stora, exempelvis upp till 5 GB för azure-docs.</span><span class="sxs-lookup"><span data-stu-id="2e75c-146">Some of the repositories can be large; up to 5 GB for azure-docs for example.</span></span> <span data-ttu-id="2e75c-147">Välj en plats med tillgängligt diskutrymme.</span><span class="sxs-lookup"><span data-stu-id="2e75c-147">Choose a location with available disk space.</span></span>

1. <span data-ttu-id="2e75c-148">Välj ett mappnamn som är lätt för dig att komma ihåg och skriva.</span><span class="sxs-lookup"><span data-stu-id="2e75c-148">Choose a folder name should be easy for you to remember and type.</span></span> <span data-ttu-id="2e75c-149">Du kan till exempel välja en rotmapp `C:\docs\` eller skapa en mapp i användarprofilens katalog `~/Documents/docs/`</span><span class="sxs-lookup"><span data-stu-id="2e75c-149">For example, consider a root folder `C:\docs\` or make a folder in your user profile directory `~/Documents/docs/`</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="2e75c-150">Undvik att välja en lokal mappsökväg som ligger inuti platsen för en annan git-lagringsplatsmapp.</span><span class="sxs-lookup"><span data-stu-id="2e75c-150">Avoid choosing a local folder path that is nested inside of another git repository folder location.</span></span> <span data-ttu-id="2e75c-151">Det går att lagra de git-klonade mapparna bredvid varandra, men kapsling av git-mappar i varandra leder till fel för filspårningen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-151">While it is acceptable to store the git cloned folders adjacent to each other, nesting git folders inside one another causes errors for the file tracking.</span></span>

2. <span data-ttu-id="2e75c-152">Starta Git Bash</span><span class="sxs-lookup"><span data-stu-id="2e75c-152">Launch Git Bash</span></span>

   ![Starta Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   <span data-ttu-id="2e75c-154">Standardplatsen där Git Bash startar är normalt i hemkatalogen (~) eller `/c/users/<Windows-user-account>/` på Windows OS.</span><span class="sxs-lookup"><span data-stu-id="2e75c-154">The default location that Git Bash starts in is typically the home directory (~) or `/c/users/<Windows-user-account>/` on Windows OS.</span></span>

   <span data-ttu-id="2e75c-155">Fastställ aktuell katalog genom att skriva `pwd` i $-fönstret.</span><span class="sxs-lookup"><span data-stu-id="2e75c-155">To determine the current directory, type `pwd` at the $ prompt.</span></span> 

3. <span data-ttu-id="2e75c-156">Ändra katalog (cd) till den mapp som du skapade för att vara lokal värd för lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-156">Change directory (cd) into the folder that you created for hosting the repository locally.</span></span> <span data-ttu-id="2e75c-157">Tänk på att Git Bash använder Linux-konventionen med snedstreck i stället för omvänt snedstreck för mappsökvägar.</span><span class="sxs-lookup"><span data-stu-id="2e75c-157">Note that Git Bash uses Linux convention of forward-slashes instead of back-slashes for folder paths.</span></span>

   <span data-ttu-id="2e75c-158">Till exempel `cd /c/docs/ ` eller `cd ~/Documents/docs/`</span><span class="sxs-lookup"><span data-stu-id="2e75c-158">For example, `cd /c/docs/ ` or `cd ~/Documents/docs/`</span></span>

## <a name="create-a-local-clone"></a><span data-ttu-id="2e75c-159">Skapa en lokal klon</span><span class="sxs-lookup"><span data-stu-id="2e75c-159">Create a local clone</span></span>

<span data-ttu-id="2e75c-160">Använd Git Bash för att förbereda för körning av kommandot **clone** som hämtar en kopia av en lagringsplats (din förgrening) till din enhet på den aktuella lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-160">Using Git Bash, prepare to run the **clone** command to pull a copy of a repository (your fork) down to your device on the current directory.</span></span> 

### <a name="authenticate-by-using-git-credential-manager"></a><span data-ttu-id="2e75c-161">Autentisera med hjälp av Git Credential Manager</span><span class="sxs-lookup"><span data-stu-id="2e75c-161">Authenticate by using Git Credential Manager</span></span>
<span data-ttu-id="2e75c-162">Om du installerade den senaste versionen av Git för Windows och godkände standardinstallationen är Git Credential Manager aktiverat som standard.</span><span class="sxs-lookup"><span data-stu-id="2e75c-162">If you installed the latest version of Git for Windows and accepted the default installation, Git Credential Manager is enabled by default.</span></span> <span data-ttu-id="2e75c-163">Git Credential Manager förenklar autentiseringen eftersom du inte behöver hämta din personliga åtkomsttoken när du återupprättar autentiserade anslutningar och fjärranslutningar med GitHub.</span><span class="sxs-lookup"><span data-stu-id="2e75c-163">Git Credential Manager makes authentication much easier, because you don't need to recall your personal access token when re-establishing authenticated connections and remotes with GitHub.</span></span>

1. <span data-ttu-id="2e75c-164">Kör kommandot **clone** genom att ange namnet på lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-164">Run the **clone** command, by providing the repository name.</span></span> <span data-ttu-id="2e75c-165">Kloning laddar ned (klonar) den förgrenade lagringsplatsen till din lokala dator.</span><span class="sxs-lookup"><span data-stu-id="2e75c-165">Cloning downloads (clone) the forked repository on your local computer.</span></span> 

    > [!Tip]
    > <span data-ttu-id="2e75c-166">Du kan hämta din förgrenings GitHub URL för kloningskommandot från knappen **Klona eller hämta** i gränssnittet i GitHub:</span><span class="sxs-lookup"><span data-stu-id="2e75c-166">You can get your fork's GitHub URL for the clone command from the **Clone or download** button in the GitHub UI:</span></span>
    >
    > ![Klona eller hämta](./media/contribute-get-started-setup-local/clone-or-download.png)

    <span data-ttu-id="2e75c-168">Se till att du anger sökvägen till *din förgrening* under kloningsprocessen, inte huvudlagringsplatsen som du skapade förgreningen från.</span><span class="sxs-lookup"><span data-stu-id="2e75c-168">Be sure to specify the path to *your fork* during the cloning process, not the main repository from which you created the fork.</span></span> <span data-ttu-id="2e75c-169">Annars kan du inte bidra med ändringar.</span><span class="sxs-lookup"><span data-stu-id="2e75c-169">Otherwise, you cannot contribute changes.</span></span> <span data-ttu-id="2e75c-170">Referenser till din förgrening sker med ditt personliga GitHub-användarkonto, t.ex. `github.com/<github-username>/<repo>`.</span><span class="sxs-lookup"><span data-stu-id="2e75c-170">Your fork is referenced through your personal GitHub user account, such as `github.com/<github-username>/<repo>`.</span></span>

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    <span data-ttu-id="2e75c-171">Kloningskommandot bör se ut så här:</span><span class="sxs-lookup"><span data-stu-id="2e75c-171">Your clone command should look similar to this example:</span></span>

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. <span data-ttu-id="2e75c-172">Ange dina autentiseringsuppgifter för GitHub när du uppmanas göra det.</span><span class="sxs-lookup"><span data-stu-id="2e75c-172">When you're prompted, enter your GitHub credentials.</span></span>

    ![GitHub-inloggning](./media/contribute-get-started-setup-local/github-login.png)

3. <span data-ttu-id="2e75c-174">När du uppmanas till detta ska du ange koden för tvåfaktorautentisering.</span><span class="sxs-lookup"><span data-stu-id="2e75c-174">When you're prompted, enter your two-factor authentication code.</span></span>

    ![GitHub, tvåfaktorautentisering](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > <span data-ttu-id="2e75c-176">Dina inloggningsuppgifter sparas och används för att autentisera framtida begäranden till GitHub.</span><span class="sxs-lookup"><span data-stu-id="2e75c-176">Your credentials will be saved and used to authenticate future GitHub requests.</span></span> <span data-ttu-id="2e75c-177">Du behöver endast göra denna autentisering en gång per dator.</span><span class="sxs-lookup"><span data-stu-id="2e75c-177">You only need to do this authentication once per computer.</span></span> 

4. <span data-ttu-id="2e75c-178">Kloningskommandot kör och laddar ned en kopia av lagringsplatsens filer från din förgrening till en ny mapp på den lokala disken.</span><span class="sxs-lookup"><span data-stu-id="2e75c-178">The clone command runs and downloads a copy of the repository files from your fork into a new folder on the local disk.</span></span> <span data-ttu-id="2e75c-179">En ny mapp skapas i den aktuella mappen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-179">A new folder is made within the current folder.</span></span> <span data-ttu-id="2e75c-180">Det kan ta några minuter, beroende på lagringsplatsens storlek.</span><span class="sxs-lookup"><span data-stu-id="2e75c-180">It may take a few minutes, depending on the repository size.</span></span> <span data-ttu-id="2e75c-181">Du kan utforska mappen för att se strukturen när den har slutförts.</span><span class="sxs-lookup"><span data-stu-id="2e75c-181">You can explore the folder to see the structure once it is finished.</span></span>

## <a name="configure-remote-upstream"></a><span data-ttu-id="2e75c-182">Konfigurera fjärransluten uppström</span><span class="sxs-lookup"><span data-stu-id="2e75c-182">Configure remote upstream</span></span>
<span data-ttu-id="2e75c-183">När du har klonat lagringsplatsen konfigurerar du en skrivskyddad anslutning till huvudlagret med namnet **upstream**.</span><span class="sxs-lookup"><span data-stu-id="2e75c-183">After cloning the repository, set up a read-only remote connection to the main repository named **upstream**.</span></span> <span data-ttu-id="2e75c-184">Du använder denna uppströms-URL för att synkronisera din lokala lagringsplats med de senaste uppdateringarna som andra deltagare har gjort.</span><span class="sxs-lookup"><span data-stu-id="2e75c-184">You use the upstream URL to keep your local repository in sync with the latest changes made by others.</span></span> <span data-ttu-id="2e75c-185">Kommandot **git remote** används för att ställa in konfigurationsvärdet.</span><span class="sxs-lookup"><span data-stu-id="2e75c-185">The **git remote** command is used to set the configuration value.</span></span> <span data-ttu-id="2e75c-186">Du använder kommandot **fetch** för att uppdatera förgreningsinformationen från uppströmslagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="2e75c-186">You use the **fetch** command to refresh the branch info from the upstream repository.</span></span>

1. <span data-ttu-id="2e75c-187">Om du använder **Git Credential Manager** ska du använda följande kommandon.</span><span class="sxs-lookup"><span data-stu-id="2e75c-187">If you're using **Git Credential Manager**, use the following commands.</span></span> <span data-ttu-id="2e75c-188">Byt ut platshållarna \<repo\> och \<organization\>.</span><span class="sxs-lookup"><span data-stu-id="2e75c-188">Replace the \<repo\> and \<organization\> placeholders.</span></span>
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. <span data-ttu-id="2e75c-189">Kontrollera de konfigurerade värdena och bekräfta att webbadresserna är korrekta.</span><span class="sxs-lookup"><span data-stu-id="2e75c-189">View the configured values and confirm the URLs are correct.</span></span> <span data-ttu-id="2e75c-190">Kontrollera att webbadresserna för **origin** leder till din personliga förgrening.</span><span class="sxs-lookup"><span data-stu-id="2e75c-190">Ensure the **origin** URLs point to your personal fork.</span></span> <span data-ttu-id="2e75c-191">Kontrollera att webbadresserna för **upstream** leder till huvudlagringsplatsen, t.ex. MicrosoftDocs eller Azure.</span><span class="sxs-lookup"><span data-stu-id="2e75c-191">Ensure the **upstream** URLs point to the main repository, such as MicrosoftDocs or Azure.</span></span> 
   ```bash
   git remote -v 
   ```

   <span data-ttu-id="2e75c-192">Ett exempel på fjärransluten utdata visas.</span><span class="sxs-lookup"><span data-stu-id="2e75c-192">Example remote output is shown.</span></span> <span data-ttu-id="2e75c-193">Ett fiktivt git-konto med namnet MyGitAccount konfigureras med en personlig åtkomsttoken för att komma åt lagringsplatsen azure-docs:</span><span class="sxs-lookup"><span data-stu-id="2e75c-193">A fictitious git account named MyGitAccount is configured with a personal access token to access the repo azure-docs:</span></span>
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. <span data-ttu-id="2e75c-194">Du kan ta bort fjärrvärdet om du har gjort ett misstag.</span><span class="sxs-lookup"><span data-stu-id="2e75c-194">If you made a mistake, you can remove the remote value.</span></span> <span data-ttu-id="2e75c-195">Ta bort uppströmsvärdet genom att köra kommandot `git remote remove upstream`.</span><span class="sxs-lookup"><span data-stu-id="2e75c-195">To remove the upstream value, run the command `git remote remove upstream`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2e75c-196">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="2e75c-196">Next steps</span></span>
- <span data-ttu-id="2e75c-197">Om du vill lära dig mer om att lägga till och uppdatera innehåll kan du fortsätta till sidan [arbetsflöden för arbete med GitHub](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="2e75c-197">To learn more about adding and updating content, continue to the [GitHub contribution workflow](how-to-write-workflows-major.md).</span></span>