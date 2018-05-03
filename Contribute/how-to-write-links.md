---
title: Använda länkar i dokumentationen
description: Den här artikeln innehåller vägledning för att skapa länkar till innehåll i docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 06/29/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1699e57ac6a4dc4c5a1ef099ea183b3cbc6307cd
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2018
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="8bfc1-103">Använda länkar i dokumentation</span><span class="sxs-lookup"><span data-stu-id="8bfc1-103">Using links in documentation</span></span>
<span data-ttu-id="8bfc1-104">Den här artikeln beskriver hur du använder hyperlänkar från sidor som finns på docs.microsoft.com. Länkar är lätta att lägga till i Markdown med få varierande konventioner.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com. Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="8bfc1-105">Länkar leder användarna till innehåll på samma sida, leder bort till intilliggande sidor eller leder till externa webbplatser och webbadresser.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-105">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="8bfc1-106">Serverdelen av webbplatsen docs.microsoft.com använder Open Publishing Services (OPS) som implementerar DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="8bfc1-106">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="8bfc1-107">DFM är mycket kompatibelt med GitHub Flavored Markdown (GFM), och DFM lägger till ytterligare funktioner via Markdown-tillägg.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-107">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bfc1-108">Alla länkar måste vara säkra (`https` mot `http`) när målet har stöd för den (vilket de flesta bör ha).</span><span class="sxs-lookup"><span data-stu-id="8bfc1-108">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="8bfc1-109">Länktext</span><span class="sxs-lookup"><span data-stu-id="8bfc1-109">Link text</span></span>

<span data-ttu-id="8bfc1-110">Ord som inkluderas i länktext ska vara enkla.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-110">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="8bfc1-111">De ska med andra ord vara vanliga ord eller rubriken på sidan som du länkar till.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-111">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bfc1-112">Använd inte ”klicka här”.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-112">Do not use "click here."</span></span> <span data-ttu-id="8bfc1-113">Det är dåligt för sökmotoroptimering och beskriver inte målet adekvat.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-113">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="8bfc1-114">**Korrekt:**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-114">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="8bfc1-115">**Inkorrekt:**</span><span class="sxs-lookup"><span data-stu-id="8bfc1-115">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="8bfc1-116">Länkar från en artikel till en annan</span><span class="sxs-lookup"><span data-stu-id="8bfc1-116">Links from one article to another</span></span>

<span data-ttu-id="8bfc1-117">Använd följande länksyntax för att skapa en infogad länk från en Docs teknisk artikel till en annan teknisk artikel i Docs inom samma dokumentuppsättning:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-117">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="8bfc1-118">En artikel i ett katalog länkar till en annan artikel i samma katalog:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-118">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="8bfc1-119">En artikel länkar från en underkatalog till en artikel i rotkatalogen:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-119">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="8bfc1-120">En artikel i rotkatalogen länkar till artikel i en underkatalog:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-120">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="8bfc1-121">En artikel i en underkatalog länkar till en artikel i en annan underkatalog:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-121">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="8bfc1-122">En artikel som länkar över dokumentuppsättningar (även om de finns i samma lagringsplats): `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="8bfc1-122">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>
  
## <a name="links-to-anchors"></a><span data-ttu-id="8bfc1-123">Länkar till fästpunkter</span><span class="sxs-lookup"><span data-stu-id="8bfc1-123">Links to anchors</span></span>

<span data-ttu-id="8bfc1-124">Du behöver inte skapa fästpunkter.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-124">You do not have to create anchors.</span></span> <span data-ttu-id="8bfc1-125">De skapas automatiskt vid publiceringstillfället för alla H2-rubriker.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-125">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="8bfc1-126">Det enda du behöver göra är att skapa länkar till H2-avsnitten.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-126">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="8bfc1-127">Länka till en rubrik inom samma artikel:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-127">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="8bfc1-128">Länka till en fästpunkt i en annan artikel i samma underkatalog:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-128">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="8bfc1-129">Länka till en fästpunkt i en annan tjänsts underkatalog:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-129">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="8bfc1-130">Länkar från inkluderar</span><span class="sxs-lookup"><span data-stu-id="8bfc1-130">Links from includes</span></span>

<span data-ttu-id="8bfc1-131">Eftersom inkluderade filer placeras i en annan katalog, måste du använda längre relativa sökvägar.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-131">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="8bfc1-132">För att länka en artikel från en inkluderad fil använder du det här formatet:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-132">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="8bfc1-133">Länkar i väljare</span><span class="sxs-lookup"><span data-stu-id="8bfc1-133">Links in selectors</span></span>

<span data-ttu-id="8bfc1-134">Om du har väljare som är inbäddade i en inkludering (precis som Azure-dokumentationsteamet) ska du använda följande länkstruktur:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-134">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="8bfc1-135">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span><span class="sxs-lookup"><span data-stu-id="8bfc1-135">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="8bfc1-136">(Text1 | Example1 )</span><span class="sxs-lookup"><span data-stu-id="8bfc1-136">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="8bfc1-137">(Text1 | Example2 )</span><span class="sxs-lookup"><span data-stu-id="8bfc1-137">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="8bfc1-138">(Text2 | Example3 )</span><span class="sxs-lookup"><span data-stu-id="8bfc1-138">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="8bfc1-139">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="8bfc1-139">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="8bfc1-140">Referensstilslänkar</span><span class="sxs-lookup"><span data-stu-id="8bfc1-140">Reference-style links</span></span>

<span data-ttu-id="8bfc1-141">Du kan använda referensstilslänkar för att göra ditt källinnehåll enklare att läsa.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-141">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="8bfc1-142">Referensstilslänkarna byter ut infogad länksyntax med en förenklad syntax som gör det möjligt för dig att flytta längs webbadresserna till slutet av artikeln.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-142">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="8bfc1-143">Här är [Daring Fireball](https://daringfireball.net/projects/markdown/)s exempel:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-143">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="8bfc1-144">Infogad text:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-144">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="8bfc1-145">Länka referenser i slutet av den här artikeln:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-145">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="8bfc1-146">Se till att du inkluderar utrymme efter kolumnen, före länken.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-146">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="8bfc1-147">När du länkar till andra tekniska artiklar kommer, om du glömmer att inkludera utrymme, länken att brytas i publiceringsartikeln.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-147">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="8bfc1-148">Länkar till sidor som inte är en del av den tekniska dokumentationsuppsättningen</span><span class="sxs-lookup"><span data-stu-id="8bfc1-148">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="8bfc1-149">För att länka en sida till en annan Microsoft-egendom (såsom en prissida, SLA-sida eller något annat som inte är en dokumentationsartikel), använder du en absolut URL, men utelämnar den lokala.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-149">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="8bfc1-150">Målet här är att länka arbete i GitHub och på den renderade webbplatsen:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-150">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="8bfc1-151">Länkar till webbplatser som tillhör tredje part</span><span class="sxs-lookup"><span data-stu-id="8bfc1-151">Links to third-party sites</span></span>

<span data-ttu-id="8bfc1-152">Den bästa användarupplevelsen minimerar sändning av användare till en annan webbplats.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-152">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="8bfc1-153">Så basera alla länkar till webbplatser som tillhör tredje part, vilket vi behöver göra ibland, på den här informationen:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-153">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="8bfc1-154">**Ansvarstagande**: Länka till tredjepartsinnehåll när det är tredjepartsinformation.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-154">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="8bfc1-155">Till exempel är det inte Microsofts uppgift att förklara hur man använder Android-utvecklingsverktyg – det är Googles uppgift.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-155">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="8bfc1-156">Om vi behöver kan vi förklara hur man använder Android-utvecklingsverktyg *med* Azure, men det är Googles uppgift att berätta hur de använder sina verktyg.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-156">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="8bfc1-157">**Kvittering av projektledare**: Begär att Microsoft kvitterar tredjepartsinnehåll.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-157">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="8bfc1-158">Genom att länka till det berättar vi något om vårt förtroende för det och vår skyldighet om människor följer instruktionerna.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-158">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="8bfc1-159">**Granska färskhet:** Kontrollera att tredjepartsinformation fortfarande är aktuell, korrekt och relevant och att länken inte har ändrats.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-159">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="8bfc1-160">**Annan webbsida:** Se till att användare är medvetna om att de går till en annan webbsida.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-160">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="8bfc1-161">Om detta inte klart framgår av innehållet lägger du till en kvalificerande mening.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-161">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="8bfc1-162">Till exempel: "Förutsättningar inkluderar Android-utvecklarverktyg, som du kan hämta från Android Studio-webbplatsen".</span><span class="sxs-lookup"><span data-stu-id="8bfc1-162">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="8bfc1-163">**Nästa steg:** Det är ok att lägga till en länk till, låt oss säga, en MVP-blogg i ett Nästa steg-avsnitt.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-163">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="8bfc1-164">Se återigen till att användarna förstår att de kommer att lämna webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-164">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="8bfc1-165">**Juridisk information:** Vi täcks juridiskt under **Länkar till webbplatser som tillhör tredje part** i fotnoten för **Användningsvillkor** på varje ms.com-sida.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-165">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="8bfc1-166">Länkar till MSDN eller TechNet</span><span class="sxs-lookup"><span data-stu-id="8bfc1-166">Links to MSDN or TechNet</span></span>

<span data-ttu-id="8bfc1-167">När du behöver länka till MSDN eller TechNet, använder du den fullständiga länken till avsnittet och tar bort språkinställningen "en-us" från länken.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-167">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="8bfc1-168">Länkar till Azure PowerShell-referensinnehåll</span><span class="sxs-lookup"><span data-stu-id="8bfc1-168">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="8bfc1-169">Azure PowerShell-referensinnehåll har gått igenom flera ändringar sedan november 2016.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-169">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="8bfc1-170">Använd följande riktlinjer för länkning till det här innehållet från andra artiklar på docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-170">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="8bfc1-171">URL-sidans struktur:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-171">Structure of the URL:</span></span>

* <span data-ttu-id="8bfc1-172">För cmdlets:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-172">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="8bfc1-173">För konceptuella ämnen:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-173">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="8bfc1-174">Delen med &lt;moniker-namnet&gt; är valfri.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-174">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="8bfc1-175">Om den utesluts kommer du att skickas till den senaste versionen av innehållet.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-175">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="8bfc1-176">Delen med &lt;tjänstnamnet&gt; är ett av de exempel som visas på följande grundläggande URL:er:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-176">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="8bfc1-177">Innehåll från Azure PowerShell (AzureRM): https://docs.microsoft.com/powershell/azure/</span><span class="sxs-lookup"><span data-stu-id="8bfc1-177">Azure PowerShell (AzureRM) content: https://docs.microsoft.com/powershell/azure/</span></span>
- <span data-ttu-id="8bfc1-178">Innehåll från Azure PowerShell (ASM): https://docs.microsoft.com/powershell/azure/_servicemanagement_</span><span class="sxs-lookup"><span data-stu-id="8bfc1-178">Azure PowerShell (ASM) content: https://docs.microsoft.com/powershell/azure/_servicemanagement_</span></span>
- <span data-ttu-id="8bfc1-179">Innehåll från Azure Active Directory (AzureAD) PowerShell: https://docs.microsoft.com/powershell/azure/_active directory_</span><span class="sxs-lookup"><span data-stu-id="8bfc1-179">Azure Active Directory (AzureAD) PowerShell content: https://docs.microsoft.com/powershell/azure/_active-directory_</span></span>
- <span data-ttu-id="8bfc1-180">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span><span class="sxs-lookup"><span data-stu-id="8bfc1-180">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span></span>
- <span data-ttu-id="8bfc1-181">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span><span class="sxs-lookup"><span data-stu-id="8bfc1-181">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span></span>
- <span data-ttu-id="8bfc1-182">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span><span class="sxs-lookup"><span data-stu-id="8bfc1-182">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span></span>

<span data-ttu-id="8bfc1-183">När du använder dessa URL:er kommer du att omdirigeras till den senaste versionen av innehållet.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-183">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="8bfc1-184">På detta sätt behöver du inte ange en versionsmoniker.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-184">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="8bfc1-185">Och du behöver inte heller ha länkar till konceptuellt innehåll som måste uppdateras när versionen ändras.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-185">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="8bfc1-186">För att skapa korrekt länk söker du upp sidan du vill länka till i din webbläsare och kopierar URL-adressen.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-186">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="8bfc1-187">Ta sedan bort https://docs.microsoft.com och informationen om nationella inställningar.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-187">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="8bfc1-188">När du länkar från en innehållsförteckning måste du använda den fullständiga URL:en utan språkinformationen.</span><span class="sxs-lookup"><span data-stu-id="8bfc1-188">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="8bfc1-189">Markdown-exempel:</span><span class="sxs-lookup"><span data-stu-id="8bfc1-189">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
