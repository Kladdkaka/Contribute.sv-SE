---
title: Använda länkar i dokumentationen
description: Den här artikeln innehåller vägledning för att skapa länkar till innehåll i docs.microsoft.com.
ms.date: 06/29/2017
ms.openlocfilehash: dad0460cfb36594c17cef1b079c5fc14191f56f7
ms.sourcegitcommit: 886ca76086a302d1d6124967df12a5bcfe4fd4b5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/10/2018
ms.locfileid: "40251423"
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="21875-103">Använda länkar i dokumentation</span><span class="sxs-lookup"><span data-stu-id="21875-103">Using links in documentation</span></span>
<span data-ttu-id="21875-104">Den här artikeln beskriver hur du använder hyperlänkar från sidor som finns på docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="21875-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com.</span></span> <span data-ttu-id="21875-105">Länkar är lätta att lägga till i Markdown med få varierande konventioner.</span><span class="sxs-lookup"><span data-stu-id="21875-105">Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="21875-106">Länkar leder användarna till innehåll på samma sida, leder bort till intilliggande sidor eller leder till externa webbplatser och webbadresser.</span><span class="sxs-lookup"><span data-stu-id="21875-106">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="21875-107">Serverdelen av webbplatsen docs.microsoft.com använder Open Publishing Services (OPS) som implementerar DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="21875-107">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="21875-108">DFM är mycket kompatibelt med GitHub Flavored Markdown (GFM), och DFM lägger till ytterligare funktioner via Markdown-tillägg.</span><span class="sxs-lookup"><span data-stu-id="21875-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21875-109">Alla länkar måste vara säkra (`https` mot `http`) när målet har stöd för den (vilket de flesta bör ha).</span><span class="sxs-lookup"><span data-stu-id="21875-109">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="21875-110">Länktext</span><span class="sxs-lookup"><span data-stu-id="21875-110">Link text</span></span>

<span data-ttu-id="21875-111">Ord som inkluderas i länktext ska vara enkla.</span><span class="sxs-lookup"><span data-stu-id="21875-111">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="21875-112">De ska med andra ord vara vanliga ord eller rubriken på sidan som du länkar till.</span><span class="sxs-lookup"><span data-stu-id="21875-112">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21875-113">Använd inte ”klicka här”.</span><span class="sxs-lookup"><span data-stu-id="21875-113">Do not use "click here."</span></span> <span data-ttu-id="21875-114">Det är dåligt för sökmotoroptimering och beskriver inte målet adekvat.</span><span class="sxs-lookup"><span data-stu-id="21875-114">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="21875-115">**Korrekt:**</span><span class="sxs-lookup"><span data-stu-id="21875-115">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="21875-116">**Inkorrekt:**</span><span class="sxs-lookup"><span data-stu-id="21875-116">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="21875-117">Länkar från en artikel till en annan</span><span class="sxs-lookup"><span data-stu-id="21875-117">Links from one article to another</span></span>

<span data-ttu-id="21875-118">Använd följande länksyntax för att skapa en infogad länk från en Docs teknisk artikel till en annan teknisk artikel i Docs inom samma dokumentuppsättning:</span><span class="sxs-lookup"><span data-stu-id="21875-118">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="21875-119">En artikel i ett katalog länkar till en annan artikel i samma katalog:</span><span class="sxs-lookup"><span data-stu-id="21875-119">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="21875-120">En artikel länkar från en underkatalog till en artikel i rotkatalogen:</span><span class="sxs-lookup"><span data-stu-id="21875-120">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="21875-121">En artikel i rotkatalogen länkar till artikel i en underkatalog:</span><span class="sxs-lookup"><span data-stu-id="21875-121">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="21875-122">En artikel i en underkatalog länkar till en artikel i en annan underkatalog:</span><span class="sxs-lookup"><span data-stu-id="21875-122">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="21875-123">En artikel som länkar över dokumentuppsättningar (även om de finns i samma lagringsplats): `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="21875-123">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21875-124">Inget av exemplen ovan använder `~/` som en del av länken.</span><span class="sxs-lookup"><span data-stu-id="21875-124">None of the above examples use the `~/` as part of the link.</span></span> <span data-ttu-id="21875-125">Om du länkar till en sökväg vid lagringsplatsens rot börjar du med `/`.</span><span class="sxs-lookup"><span data-stu-id="21875-125">If you are linking to a path at the root of the repository, start with the `/`.</span></span> <span data-ttu-id="21875-126">Om `~/` tas med skapas ogiltiga länkar vid navigering på källagringsplatserna på GitHub.</span><span class="sxs-lookup"><span data-stu-id="21875-126">Including the `~/` produces invalid links when navigating the source repositories on GitHub.</span></span> <span data-ttu-id="21875-127">Om sökvägen börjar med `/` blir matchningen korrekt.</span><span class="sxs-lookup"><span data-stu-id="21875-127">Starting the path with `/` resolves correctly.</span></span>

## <a name="links-to-anchors"></a><span data-ttu-id="21875-128">Länkar till fästpunkter</span><span class="sxs-lookup"><span data-stu-id="21875-128">Links to anchors</span></span>

<span data-ttu-id="21875-129">Du behöver inte skapa fästpunkter.</span><span class="sxs-lookup"><span data-stu-id="21875-129">You do not have to create anchors.</span></span> <span data-ttu-id="21875-130">De skapas automatiskt vid publiceringstillfället för alla H2-rubriker.</span><span class="sxs-lookup"><span data-stu-id="21875-130">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="21875-131">Det enda du behöver göra är att skapa länkar till H2-avsnitten.</span><span class="sxs-lookup"><span data-stu-id="21875-131">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="21875-132">Länka till en rubrik inom samma artikel:</span><span class="sxs-lookup"><span data-stu-id="21875-132">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="21875-133">Länka till en fästpunkt i en annan artikel i samma underkatalog:</span><span class="sxs-lookup"><span data-stu-id="21875-133">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="21875-134">Länka till en fästpunkt i en annan tjänsts underkatalog:</span><span class="sxs-lookup"><span data-stu-id="21875-134">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="21875-135">Länkar från inkluderar</span><span class="sxs-lookup"><span data-stu-id="21875-135">Links from includes</span></span>

<span data-ttu-id="21875-136">Eftersom inkluderade filer placeras i en annan katalog, måste du använda längre relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="21875-136">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="21875-137">För att länka en artikel från en inkluderad fil använder du det här formatet:</span><span class="sxs-lookup"><span data-stu-id="21875-137">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="21875-138">Länkar i väljare</span><span class="sxs-lookup"><span data-stu-id="21875-138">Links in selectors</span></span>

<span data-ttu-id="21875-139">Om du har väljare som är inbäddade i en inkludering (precis som Azure-dokumentationsteamet) ska du använda följande länkstruktur:</span><span class="sxs-lookup"><span data-stu-id="21875-139">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="21875-140">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span><span class="sxs-lookup"><span data-stu-id="21875-140">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="21875-141">(Text1 | Example1 )</span><span class="sxs-lookup"><span data-stu-id="21875-141">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="21875-142">(Text1 | Example2 )</span><span class="sxs-lookup"><span data-stu-id="21875-142">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="21875-143">(Text2 | Example3 )</span><span class="sxs-lookup"><span data-stu-id="21875-143">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="21875-144">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="21875-144">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="21875-145">Referensstilslänkar</span><span class="sxs-lookup"><span data-stu-id="21875-145">Reference-style links</span></span>

<span data-ttu-id="21875-146">Du kan använda referensstilslänkar för att göra ditt källinnehåll enklare att läsa.</span><span class="sxs-lookup"><span data-stu-id="21875-146">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="21875-147">Referensstilslänkarna byter ut infogad länksyntax med en förenklad syntax som gör det möjligt för dig att flytta längs webbadresserna till slutet av artikeln.</span><span class="sxs-lookup"><span data-stu-id="21875-147">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="21875-148">Här är [Daring Fireball](https://daringfireball.net/projects/markdown/)s exempel:</span><span class="sxs-lookup"><span data-stu-id="21875-148">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="21875-149">Infogad text:</span><span class="sxs-lookup"><span data-stu-id="21875-149">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="21875-150">Länka referenser i slutet av den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="21875-150">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="21875-151">Se till att du inkluderar utrymme efter kolumnen, före länken.</span><span class="sxs-lookup"><span data-stu-id="21875-151">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="21875-152">När du länkar till andra tekniska artiklar kommer, om du glömmer att inkludera utrymme, länken att brytas i publiceringsartikeln.</span><span class="sxs-lookup"><span data-stu-id="21875-152">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="21875-153">Länkar till sidor som inte är en del av den tekniska dokumentationsuppsättningen</span><span class="sxs-lookup"><span data-stu-id="21875-153">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="21875-154">För att länka en sida till en annan Microsoft-egendom (såsom en prissida, SLA-sida eller något annat som inte är en dokumentationsartikel), använder du en absolut URL, men utelämnar den lokala.</span><span class="sxs-lookup"><span data-stu-id="21875-154">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="21875-155">Målet här är att länka arbete i GitHub och på den renderade webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="21875-155">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="21875-156">Länkar till webbplatser som tillhör tredje part</span><span class="sxs-lookup"><span data-stu-id="21875-156">Links to third-party sites</span></span>

<span data-ttu-id="21875-157">Den bästa användarupplevelsen minimerar sändning av användare till en annan webbplats.</span><span class="sxs-lookup"><span data-stu-id="21875-157">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="21875-158">Så basera alla länkar till webbplatser som tillhör tredje part, vilket vi behöver göra ibland, på den här informationen:</span><span class="sxs-lookup"><span data-stu-id="21875-158">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="21875-159">**Ansvarstagande**: Länka till tredjepartsinnehåll när det är tredjepartsinformation.</span><span class="sxs-lookup"><span data-stu-id="21875-159">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="21875-160">Till exempel är det inte Microsofts uppgift att förklara hur man använder Android-utvecklingsverktyg – det är Googles uppgift.</span><span class="sxs-lookup"><span data-stu-id="21875-160">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="21875-161">Om vi behöver kan vi förklara hur man använder Android-utvecklingsverktyg *med* Azure, men det är Googles uppgift att berätta hur de använder sina verktyg.</span><span class="sxs-lookup"><span data-stu-id="21875-161">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="21875-162">**Kvittering av projektledare**: Begär att Microsoft kvitterar tredjepartsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="21875-162">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="21875-163">Genom att länka till det berättar vi något om vårt förtroende för det och vår skyldighet om människor följer instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="21875-163">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="21875-164">**Granska färskhet:** Kontrollera att tredjepartsinformation fortfarande är aktuell, korrekt och relevant och att länken inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="21875-164">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="21875-165">**Annan webbsida:** Se till att användare är medvetna om att de går till en annan webbsida.</span><span class="sxs-lookup"><span data-stu-id="21875-165">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="21875-166">Om detta inte klart framgår av innehållet lägger du till en kvalificerande mening.</span><span class="sxs-lookup"><span data-stu-id="21875-166">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="21875-167">Till exempel: "Förutsättningar inkluderar Android-utvecklarverktyg, som du kan hämta från Android Studio-webbplatsen".</span><span class="sxs-lookup"><span data-stu-id="21875-167">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="21875-168">**Nästa steg:** Det är ok att lägga till en länk till, låt oss säga, en MVP-blogg i ett Nästa steg-avsnitt.</span><span class="sxs-lookup"><span data-stu-id="21875-168">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="21875-169">Se återigen till att användarna förstår att de kommer att lämna webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="21875-169">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="21875-170">**Juridisk information:** Vi täcks juridiskt under **Länkar till webbplatser som tillhör tredje part** i fotnoten för **Användningsvillkor** på varje ms.com-sida.</span><span class="sxs-lookup"><span data-stu-id="21875-170">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="21875-171">Länkar till MSDN eller TechNet</span><span class="sxs-lookup"><span data-stu-id="21875-171">Links to MSDN or TechNet</span></span>

<span data-ttu-id="21875-172">När du behöver länka till MSDN eller TechNet, använder du den fullständiga länken till avsnittet och tar bort språkinställningen "en-us" från länken.</span><span class="sxs-lookup"><span data-stu-id="21875-172">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="21875-173">Länkar till Azure PowerShell-referensinnehåll</span><span class="sxs-lookup"><span data-stu-id="21875-173">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="21875-174">Azure PowerShell-referensinnehåll har gått igenom flera ändringar sedan november 2016.</span><span class="sxs-lookup"><span data-stu-id="21875-174">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="21875-175">Använd följande riktlinjer för länkning till det här innehållet från andra artiklar på docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="21875-175">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="21875-176">URL-sidans struktur:</span><span class="sxs-lookup"><span data-stu-id="21875-176">Structure of the URL:</span></span>

* <span data-ttu-id="21875-177">För cmdlets:</span><span class="sxs-lookup"><span data-stu-id="21875-177">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="21875-178">För konceptuella ämnen:</span><span class="sxs-lookup"><span data-stu-id="21875-178">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="21875-179">Delen med &lt;moniker-namnet&gt; är valfri.</span><span class="sxs-lookup"><span data-stu-id="21875-179">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="21875-180">Om den utesluts kommer du att skickas till den senaste versionen av innehållet.</span><span class="sxs-lookup"><span data-stu-id="21875-180">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="21875-181">Delen med &lt;tjänstnamnet&gt; är ett av de exempel som visas på följande grundläggande URL:er:</span><span class="sxs-lookup"><span data-stu-id="21875-181">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="21875-182">Innehåll från Azure PowerShell (AzureRM): [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="21875-182">Azure PowerShell (AzureRM) content: [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span></span>
- <span data-ttu-id="21875-183">Innehåll från Azure PowerShell (ASM): [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span><span class="sxs-lookup"><span data-stu-id="21875-183">Azure PowerShell (ASM) content: [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span></span>
- <span data-ttu-id="21875-184">Innehåll från Azure Active Directory (AzureAD) PowerShell: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span><span class="sxs-lookup"><span data-stu-id="21875-184">Azure Active Directory (AzureAD) PowerShell content: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span></span>
- <span data-ttu-id="21875-185">Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)</span><span class="sxs-lookup"><span data-stu-id="21875-185">Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)</span></span>
- <span data-ttu-id="21875-186">Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span><span class="sxs-lookup"><span data-stu-id="21875-186">Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span></span>
- <span data-ttu-id="21875-187">Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span><span class="sxs-lookup"><span data-stu-id="21875-187">Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span></span>

<span data-ttu-id="21875-188">När du använder dessa URL:er kommer du att omdirigeras till den senaste versionen av innehållet.</span><span class="sxs-lookup"><span data-stu-id="21875-188">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="21875-189">På detta sätt behöver du inte ange en versionsmoniker.</span><span class="sxs-lookup"><span data-stu-id="21875-189">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="21875-190">Och du behöver inte heller ha länkar till konceptuellt innehåll som måste uppdateras när versionen ändras.</span><span class="sxs-lookup"><span data-stu-id="21875-190">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="21875-191">För att skapa korrekt länk söker du upp sidan du vill länka till i din webbläsare och kopierar URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="21875-191">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="21875-192">Ta sedan bort https://docs.microsoft.com och informationen om nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="21875-192">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="21875-193">När du länkar från en innehållsförteckning måste du använda den fullständiga URL:en utan språkinformationen.</span><span class="sxs-lookup"><span data-stu-id="21875-193">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="21875-194">Markdown-exempel:</span><span class="sxs-lookup"><span data-stu-id="21875-194">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
