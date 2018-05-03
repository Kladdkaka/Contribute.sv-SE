---
title: Information om Git och GitHub för dokumentation
description: Den här artikeln innehåller en översikt för Git, GitHub-lagringsplats och hur innehåll ordnas, samt namngivningskonventioner som används för docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 06/30/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 5ad2ca323b680078c2bfd2fc4cac6fb1883c411f
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2018
---
# <a name="git-and-github-essentials-for-docs"></a>Information om Git och GitHub för Docs

## <a name="overview"></a>Översikt

Som deltagare som bidrar till Docs-innehåll använder du flera olika verktyg och processer. Du arbetar parallellt med andra deltagare i samma projekt, eventuellt med exakt samma innehåll, och precis samtidigt. Allt detta görs möjligt via programvaran Git och GitHub.

Git är ett versionskontrollsystem med öppen källkod. Det möjliggör den här typen av projektsamarbete via *distribuerad versionskontroll* av filer som inhyses i *lagringsplatser*. I stort gör Git det möjligt att interagera strömmar av arbete som görs av flera deltagare över tid, för en given lagringsplats.

GitHub är en webbaserad värdtjänst för Git-lagringsplatser som de som används för att lagra [docs.microsoft.com](https://docs.microsoft.com)-innehåll. För alla projekt är GitHub värd åt huvudlagringsplatsen, från vilken deltagare kan göra kopior för sitt eget arbete.

## <a name="git"></a>Git

Om du är bekant med centraliserade versionskontrollsystem (såsom Team Foundation Server, SharePoint eller Visual SourceSafe), kommer du att märka att Git har ett unikt bidragsarbetsflöde och terminologi som stöd för sin distribuerade modell. Det finns t.ex. ingen fillåsning, vilket normalt associeras med utcheckningar/incheckningar. Det är till och med så att Git tar hänsyn till ändringar på en ännu finare precisionsnivå, och jämför filer på byte per byte.

Git använder en nivåindelad struktur för att lagra och hantera innehåll för ett projekt:

- *Lagringsplats*: Också känt som en *repo*, det här är den högsta lagringsenheten. En lagringsplats innehåller en eller flera grenar.
- *Gren*: En enhet lagringsutrymme som innehåller de filer och mappar som bildar ett projekts innehåll. Grenar separerar arbetsströmmar (kallas oftast versioner). Bidrag görs alltid i en viss gren. Alla lagringsplatser innehåller en standardgren (huvudgrenen, namnges ofta som "master") och en eller flera grenar som ska slås samman med huvudgrenen. Huvudgrenen fungerar som den aktuella versionen och projektets "enda sanna källa". Den är den överordnade grenen från vilken alla andra grenar i lagringsplatsen skapas.

Deltagare interagerar med Git för att uppdatera och ändra lagringsplatser på både lokal nivå och på GitHub-nivå:

- Lokalt via verktyg som Git Bash-konsolen som har stöd för Git-kommandon för att hantera lokala lagringsplatser och kommunicera med GitHub-lagringsplatser
- Via [www.github.com](https://www.github.com), som integrerar Git för att hantera avstämningen av bidrag som flödar tillbaka till huvudlagringsplatsen

## <a name="github"></a>GitHub

> [!NOTE]
> Även om Docs-vägledning baseras på användning av GitHub, använder vissa team Visual Studio Team Services som värd för Git-lagringsplatser. Visual Studio Team Explorer-klienten har ett GUI för att interagera med Team Services-lagringsplatser, som är ett alternativ till att använda Git-kommandon via en kommandorad.
> </br>
> Många av riktlinjerna nedan utvecklades även som bästa praxis från flera år av erfarenhet i att vara värd åt Azure-tjänstinnehåll i GitHub. De kan krävas i vissa Docs-lagringsplatser.

Alla arbetsflöden börjar och slutar på GitHub-nivån, där huvudlagringsplatsen för alla Docs-projekt förvaras. De kopior som deltagare skapar för sin egen användning distribueras på flera datorer. Dessa kopior stäms så småningom av mot projektets huvudsakliga GitHub-lagringsplats.

### <a name="directory-organization"></a>Organisering av katalog

Såsom nämnts tidigare fungerar ett projekts standard-/huvudgren som den aktuella versionen av projektets innehåll. Innehållet i huvudgrenen – och grenar skapade från den – motsvarar löst organisationen av artiklarna på motsvarande Docs-sidor. Underkataloger används för separation av innehåll (såsom tjänster), mediainnehåll (såsom bildfiler) och "inkluderar" filer (som gör det möjligt att återanvända innehåll).

Du hittar normalt en `articles`-huvudkatalogen vid lagringsplatsens rot. Artikelkatalogen innehåller en uppsättning underkataloger. Artiklar i underkatalogerna är formaterade som Markdown-filer som använder ett *MD*-tillägg. Vissa lagringsplatser som har stöd för flera tjänster använder en allmän `/articles`-underkatalog, t.ex. lagringsplatsen [https://github.com/microsoft/Azure-Docs](https://github.com/microsoft/Azure-Docs). Andra kan använda ett tjänstespecifikt namn, t.ex. lagringsplatsen [https://github.com/microsoft/IntuneDocs](https://github.com/microsoft/IntuneDocs) som använder `/IntuneDocs`.

I den här katalogens rot hittar du allmänna artiklar som relaterar till den allmänna tjänsten eller produkten. Normalt kan du sedan hitta ytterligare en serie underkataloger som matchar funktioner/tjänster eller vanliga situationer. Exempelvis finns Azure-artiklarna om virtuella datorer i `/virtual-machines`-underkatalogen, de beskrivande Intune-artiklarna i `/understand-explore`-underkatalogen, o.s.v.

### <a name="media-subdirectory"></a>Underkatalog för media

Varje artikelkatalog innehåller en `/media`-underkatalog för motsvarande mediafiler. Mediafiler innehåller bilder som används i artiklar som har bildreferenser.

### <a name="includes-subdirectory"></a>Inkluderar underkatalog

När vi har innehåll som kan återanvändas som delas mellan två eller flera artiklar placeras det i en `/includes`-underkatalog fristående från `articles`-huvudkatalogen. I en Markdown-fil där den inkluderade filen används placeras motsvarande Markdown-inkluderingstillägg på den plats där hänvisningen till inkluderingsfilen ska vara.

Du hittar ytterligare vägledning i [Hur man använder Markdown: Inkluderar](how-to-write-use-markdown.md#includes).

### <a name="markdown-file-template"></a>Markdown-filmall

Av praktiska skäl innehåller rotkatalogen för varje lagringsplats normalt Markdown-mall med namnet `template.md`. Du kan använda den här mallen som en startfil om du behöver skapa en ny artikel till lagringsplatsen. Filen innehåller följande:

- Ett **metadatahuvud** längst upp i filen, avgränsat med två rader med 3 bindestreck. Den innehåller de olika taggar som används för att spåra information som rör artikeln. Metadata om en artikel krävs för vissa funktioner, till exempel författarattribution, bidragsattribution, synliga sökvägar och artikelbeskrivningar. Det omfattar också sökmotorsoptimeringar och rapporteringsprocesser som Microsoft använder för att utvärdera innehållets prestanda. Metadata är alltså viktigt!
- Ett **metadataavsnitt** som beskriver de olika metadatataggarna och -värdena. Om du är osäker på vilka värden som ska användas för metadataavsnittet kan du låta dem vara tomma, eller kommentera dem med en inledande hashtagg (#) så kommer de att granskas/fyllas i av den som granskar pull-begäran för lagringsplatsen.
- Olika **exempel på användning av Markdown** vid formatering av delarna i en artikel.
- Allmänna **anvisningar om användning av Markdown-tillägg**, som du kan använda för olika typer av aviseringar.
- Exempel på **att bädda in en video** med hjälp av en iframe.
- Allmänna **anvisningar om användning av docs.microsoft.com-tillägg** som du kan använda för särskilda kontroller, till exempel knappar och väljare.

## <a name="pull-requests"></a>Pull-begäranden

En *pull-begäran* är ett enkelt sätt för deltagare att föreslå en uppsättning ändringar som ska appliceras på standardgrenen. Ändringarna (även kända som *allokeringar*) lagras i deltagarens gren, vilket gör det möjligt för GitHub att modellera deras påverkan då de *slås samman* med standardgrenen. En pull-begäran fungerar också som en mekanism för att förse deltagaren med feedback från en bygg-/valideringsprocess, pull-begäransgranskaren, för att lösa eventuella frågor innan ändringarna slås samman med standardgrenen.

Det finns två sätt att bidra med pull-begäran, beroende på storleken på de ändringar du vill föreslå. Vi går igenom detta mer i detalj i avsnittet om [GitHub-arbetsflödet](light-workflow.md) senare i den här guiden.

<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
<!---- NOTE: these links are saved for future use in another/new article; no longer used above in this article --->
[Visual-Studio-Page]:(https://docs.microsoft.com/en-us/visualstudio/index)
[Visual-Studio-Repo-Internal]:(https://github.com/Microsoft/vsdocs)
[Visual-Studio-Repo-External]:(https://github.com/Microsoft/visualstudio-docs)
[Visual-Studio-SO]: (https://stackoverflow.com/search?q=Visual+Studio+2017)
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp
[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: https://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: https://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: https://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: https://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: https://stackoverflow.com/tags
[Forum-SO-Intune]: https://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: https://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: https://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: https://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/
