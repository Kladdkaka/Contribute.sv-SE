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
# <a name="set-up-git-repository-locally-for-documentation"></a>Ställ in Git-lagringsplatsen lokalt för dokumentation

Den här artikeln beskriver stegen för att ställa in en git-lagringsplats på din lokala dator, i syfte att bidra till Microsoft-dokumentationen. Deltagare kan använda en lokalt klonad lagringsplats för att lägga till nya artiklar, utföra större ändringar i befintliga artiklar eller ändra bilder.

Du kan köra de här engångsaktiviteterna för konfiguration för att komma igång och bidra:
> [!div class="checklist"]
> * Fastställ en lämplig lagringsplats
> * Förgrena lagringsplatsen till ditt GitHub-konto
> * Välj en lokal mapp för de klonade filerna
> * Klona lagringsplatsen till din lokala dator
> * Konfigurera det överordnade fjärrvärdet

> [!IMPORTANT]
> Om du bara gör mindre ändringar i en artikel behöver du *inte* slutföra stegen i den här artikeln. Du kan fortsätta direkt till [arbetsflödet för snabba ändringar](index.md#quick-edits-to-existing-documents).
>

## <a name="overview"></a>Översikt

För att bidra till Microsofts dokumentationswebbplats, kan du skapa och redigera Markdown-filer lokalt genom att klona motsvarande dokumentationslager. Microsoft kräver att du förgrenar den lämpliga lagringsplatsen till ditt eget github-konto så att du har läs-/skrivbehörigheter där att lagra dina föreslagna ändringar. Du kan sedan använda pull-begäranden för att slå samman ändringar i den skrivskyddade centrala delade lagringsplatsen.

![GitHub-triangeln](./media/git-and-github-initial-setup.png)

Om du är en ny användare av GitHub kan du titta på följande video som innehåller en översikt över förgrening och kloning:

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a>Fastställ lagringsplatsen

Dokumentation som finns på [docs.microsoft.com](https://docs.microsoft.com) befinner sig i flera olika lagringsplatser på [github.com](https://www.github.com).

1. Om du är osäker på vilken lagringsplats du ska använda, kan du gå till artikeln på docs.microsoft.com med din webbläsare. Välj **Redigera**-länken (pennikonen) i det övre högra hörnet på artikeln.

   ![Klicka på Redigera för att se lagringsplatsen och filplatsen.](media/index/edit-article.png)

2. Länken tar dig till github.com-platsen för motsvarande Markdown-fil i lämplig lagringsplats. Lägg märke till URL:en för att se lagringsplatsens namn.

   ![Lägg märke till URL:en för att lagringsplatsen.](media/public-repo.png)

   De här populära lagringsplatserna finns till exempel tillgängliga för offentliga bidrag:
   - Azure-dokumentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)
   - Dokumentation om SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)
   - Visual Studio-dokumentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)
   - .NET-dokumentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)
   - Azure .Net SDK-dokumentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)

## <a name="fork-the-repository"></a>Förgrena lagringsplatsen
Använd lämplig lagringsplats för att skapa en förgrening av lagringsplatsen till ditt eget GitHub-konto med hjälp av GitHub-webbplatsen.

En personlig förgrening krävs eftersom alla huvudsakliga dokumentationslagringsplatser endast ger läsbehörighet, vilket innebär att du inte kan ändra innehåll i lagringsplatsen direkt. För att utföra ändringar måste du skicka in en [pull-begäran](git-github-fundamentals.md#pull-requests) från förgreningen till huvudlagringsplatsen. Den här processen förenklas om du först har en kopia av lagringsplatsen där du har skrivbehörighet. En GitHub-*förgrening* har denna funktion.

1. Gå till huvudlagringsplatsens GitHub-sida och klicka på knappen **Förgrening** längst upp till höger.

   ![Exempel på GitHub-profil](./media/contribute-get-started-setup-local/fork.png)

2. Om du uppmanas om detta ska du välja en GitHub-kontoikon som destination för förgreningen. Detta skapar en kopia av lagringsplatsen i ditt GitHub-konto, vilket kallas en förgrening.

## <a name="choose-a-local-folder"></a>Välj en lokal mapp
Skapa en lokal mapp för att lagra en lokal kopia av lagringsplatsen. En del lagringsplatser kan vara stora, exempelvis upp till 5 GB för azure-docs. Välj en plats med tillgängligt diskutrymme.

1. Välj ett mappnamn som är lätt för dig att komma ihåg och skriva. Du kan till exempel välja en rotmapp `C:\docs\` eller skapa en mapp i användarprofilens katalog `~/Documents/docs/`

   > [!IMPORTANT]
   > Undvik att välja en lokal mappsökväg som ligger inuti platsen för en annan git-lagringsplatsmapp. Det går att lagra de git-klonade mapparna bredvid varandra, men kapsling av git-mappar i varandra leder till fel för filspårningen.

2. Starta Git Bash

   ![Starta Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   Standardplatsen där Git Bash startar är normalt i hemkatalogen (~) eller `/c/users/<Windows-user-account>/` på Windows OS.

   Fastställ aktuell katalog genom att skriva `pwd` i $-fönstret. 

3. Ändra katalog (cd) till den mapp som du skapade för att vara lokal värd för lagringsplatsen. Tänk på att Git Bash använder Linux-konventionen med snedstreck i stället för omvänt snedstreck för mappsökvägar.

   Till exempel `cd /c/docs/ ` eller `cd ~/Documents/docs/`

## <a name="create-a-local-clone"></a>Skapa en lokal klon

Använd Git Bash för att förbereda för körning av kommandot **clone** som hämtar en kopia av en lagringsplats (din förgrening) till din enhet på den aktuella lagringsplatsen. 

### <a name="authenticate-by-using-git-credential-manager"></a>Autentisera med hjälp av Git Credential Manager
Om du installerade den senaste versionen av Git för Windows och godkände standardinstallationen är Git Credential Manager aktiverat som standard. Git Credential Manager förenklar autentiseringen eftersom du inte behöver hämta din personliga åtkomsttoken när du återupprättar autentiserade anslutningar och fjärranslutningar med GitHub.

1. Kör kommandot **clone** genom att ange namnet på lagringsplatsen. Kloning laddar ned (klonar) den förgrenade lagringsplatsen till din lokala dator. 

    > [!Tip]
    > Du kan hämta din förgrenings GitHub URL för kloningskommandot från knappen **Klona eller hämta** i gränssnittet i GitHub:
    >
    > ![Klona eller hämta](./media/contribute-get-started-setup-local/clone-or-download.png)

    Se till att du anger sökvägen till *din förgrening* under kloningsprocessen, inte huvudlagringsplatsen som du skapade förgreningen från. Annars kan du inte bidra med ändringar. Referenser till din förgrening sker med ditt personliga GitHub-användarkonto, t.ex. `github.com/<github-username>/<repo>`.

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    Kloningskommandot bör se ut så här:

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. Ange dina autentiseringsuppgifter för GitHub när du uppmanas göra det.

    ![GitHub-inloggning](./media/contribute-get-started-setup-local/github-login.png)

3. När du uppmanas till detta ska du ange koden för tvåfaktorautentisering.

    ![GitHub, tvåfaktorautentisering](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > Dina inloggningsuppgifter sparas och används för att autentisera framtida begäranden till GitHub. Du behöver endast göra denna autentisering en gång per dator. 

4. Kloningskommandot kör och laddar ned en kopia av lagringsplatsens filer från din förgrening till en ny mapp på den lokala disken. En ny mapp skapas i den aktuella mappen. Det kan ta några minuter, beroende på lagringsplatsens storlek. Du kan utforska mappen för att se strukturen när den har slutförts.

## <a name="configure-remote-upstream"></a>Konfigurera fjärransluten uppström
När du har klonat lagringsplatsen konfigurerar du en skrivskyddad anslutning till huvudlagret med namnet **upstream**. Du använder denna uppströms-URL för att synkronisera din lokala lagringsplats med de senaste uppdateringarna som andra deltagare har gjort. Kommandot **git remote** används för att ställa in konfigurationsvärdet. Du använder kommandot **fetch** för att uppdatera förgreningsinformationen från uppströmslagringsplatsen.

1. Om du använder **Git Credential Manager** ska du använda följande kommandon. Byt ut platshållarna \<repo\> och \<organization\>.
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. Kontrollera de konfigurerade värdena och bekräfta att webbadresserna är korrekta. Kontrollera att webbadresserna för **origin** leder till din personliga förgrening. Kontrollera att webbadresserna för **upstream** leder till huvudlagringsplatsen, t.ex. MicrosoftDocs eller Azure. 
   ```bash
   git remote -v 
   ```

   Ett exempel på fjärransluten utdata visas. Ett fiktivt git-konto med namnet MyGitAccount konfigureras med en personlig åtkomsttoken för att komma åt lagringsplatsen azure-docs:
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. Du kan ta bort fjärrvärdet om du har gjort ett misstag. Ta bort uppströmsvärdet genom att köra kommandot `git remote remove upstream`.

## <a name="next-steps"></a>Nästa steg
- Om du vill lära dig mer om att lägga till och uppdatera innehåll kan du fortsätta till sidan [arbetsflöden för arbete med GitHub](how-to-write-workflows-major.md).