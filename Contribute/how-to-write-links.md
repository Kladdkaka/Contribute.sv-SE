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
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469542"
---
# <a name="using-links-in-documentation"></a>Använda länkar i dokumentation
Den här artikeln beskriver hur du använder hyperlänkar från sidor som finns på docs.microsoft.com. Länkar är lätta att lägga till i Markdown med få varierande konventioner. Länkar leder användarna till innehåll på samma sida, leder bort till intilliggande sidor eller leder till externa webbplatser och webbadresser.

Serverdelen av webbplatsen docs.microsoft.com använder Open Publishing Services (OPS) som implementerar DocFX Flavored Markdown (DFM). DFM är mycket kompatibelt med GitHub Flavored Markdown (GFM), och DFM lägger till ytterligare funktioner via Markdown-tillägg.

> [!IMPORTANT]
> Alla länkar måste vara säkra (`https` mot `http`) när målet har stöd för den (vilket de flesta bör ha).

## <a name="link-text"></a>Länktext

Ord som inkluderas i länktext ska vara enkla. De ska med andra ord vara vanliga ord eller rubriken på sidan som du länkar till.

> [!IMPORTANT]
> Använd inte ”klicka här”. Det är dåligt för sökmotoroptimering och beskriver inte målet adekvat.

**Korrekt:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Inkorrekt:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>Länkar från en artikel till en annan

Använd följande länksyntax för att skapa en infogad länk från en Docs teknisk artikel till en annan teknisk artikel i Docs inom samma dokumentuppsättning:

- En artikel i ett katalog länkar till en annan artikel i samma katalog:

  `[link text](article-name.md)`

- En artikel länkar från en underkatalog till en artikel i rotkatalogen:

  `[link text](../article-name.md)`

- En artikel i rotkatalogen länkar till artikel i en underkatalog:

  `[link text](./directory/article-name.md)`

- En artikel i en underkatalog länkar till en artikel i en annan underkatalog:

  `[link text](../directory/article-name.md)`

- En artikel som länkar över dokumentuppsättningar (även om de finns i samma lagringsplats): `[link text](./directory/article-name)`
  
## <a name="links-to-anchors"></a>Länkar till fästpunkter

Du behöver inte skapa fästpunkter. De skapas automatiskt vid publiceringstillfället för alla H2-rubriker. Det enda du behöver göra är att skapa länkar till H2-avsnitten.

- Länka till en rubrik inom samma artikel:

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- Länka till en fästpunkt i en annan artikel i samma underkatalog:

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- Länka till en fästpunkt i en annan tjänsts underkatalog:

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a>Länkar från inkluderar

Eftersom inkluderade filer placeras i en annan katalog, måste du använda längre relativa sökvägar. För att länka en artikel från en inkluderad fil använder du det här formatet:

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a>Länkar i väljare

Om du har väljare som är inbäddade i en inkludering (precis som Azure-dokumentationsteamet) ska du använda följande länkstruktur:

    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
    - [(Text1 | Example1 )](../articles/folder/article-name1.md)
    - [(Text1 | Example2 )](../articles/folder/article-name2.md)
    - [(Text2 | Example3 )](../articles/folder/article-name3.md)
    - [(Text2 | Example4 )](../articles/folder/article-name4.md) -->

## <a name="reference-style-links"></a>Referensstilslänkar

Du kan använda referensstilslänkar för att göra ditt källinnehåll enklare att läsa. Referensstilslänkarna byter ut infogad länksyntax med en förenklad syntax som gör det möjligt för dig att flytta längs webbadresserna till slutet av artikeln. Här är [Daring Fireball](https://daringfireball.net/projects/markdown/)s exempel:

Infogad text:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Länka referenser i slutet av den här artikeln:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

Se till att du inkluderar utrymme efter kolumnen, före länken. När du länkar till andra tekniska artiklar kommer, om du glömmer att inkludera utrymme, länken att brytas i publiceringsartikeln.

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a>Länkar till sidor som inte är en del av den tekniska dokumentationsuppsättningen

För att länka en sida till en annan Microsoft-egendom (såsom en prissida, SLA-sida eller något annat som inte är en dokumentationsartikel), använder du en absolut URL, men utelämnar den lokala. Målet här är att länka arbete i GitHub och på den renderade webbplatsen:

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a>Länkar till webbplatser som tillhör tredje part

Den bästa användarupplevelsen minimerar sändning av användare till en annan webbplats. Så basera alla länkar till webbplatser som tillhör tredje part, vilket vi behöver göra ibland, på den här informationen:

- **Ansvarstagande**: Länka till tredjepartsinnehåll när det är tredjepartsinformation. Till exempel är det inte Microsofts uppgift att förklara hur man använder Android-utvecklingsverktyg – det är Googles uppgift. Om vi behöver kan vi förklara hur man använder Android-utvecklingsverktyg *med* Azure, men det är Googles uppgift att berätta hur de använder sina verktyg.
- **Kvittering av projektledare**: Begär att Microsoft kvitterar tredjepartsinnehåll. Genom att länka till det berättar vi något om vårt förtroende för det och vår skyldighet om människor följer instruktionerna.
- **Granska färskhet:** Kontrollera att tredjepartsinformation fortfarande är aktuell, korrekt och relevant och att länken inte har ändrats.
- **Annan webbsida:** Se till att användare är medvetna om att de går till en annan webbsida. Om detta inte klart framgår av innehållet lägger du till en kvalificerande mening. Till exempel: "Förutsättningar inkluderar Android-utvecklarverktyg, som du kan hämta från Android Studio-webbplatsen".
- **Nästa steg:** Det är ok att lägga till en länk till, låt oss säga, en MVP-blogg i ett Nästa steg-avsnitt. Se återigen till att användarna förstår att de kommer att lämna webbplatsen.
- **Juridisk information:** Vi täcks juridiskt under **Länkar till webbplatser som tillhör tredje part** i fotnoten för **Användningsvillkor** på varje ms.com-sida.

## <a name="links-to-msdn-or-technet"></a>Länkar till MSDN eller TechNet

När du behöver länka till MSDN eller TechNet, använder du den fullständiga länken till avsnittet och tar bort språkinställningen "en-us" från länken.

## <a name="links-to-azure-powershell-reference-content"></a>Länkar till Azure PowerShell-referensinnehåll

Azure PowerShell-referensinnehåll har gått igenom flera ändringar sedan november 2016. Använd följande riktlinjer för länkning till det här innehållet från andra artiklar på docs.microsoft.com.

URL-sidans struktur:

* För cmdlets:
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* För konceptuella ämnen:
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

Delen med &lt;moniker-namnet&gt; är valfri. Om den utesluts kommer du att skickas till den senaste versionen av innehållet. Delen med &lt;tjänstnamnet&gt; är ett av de exempel som visas på följande grundläggande URL:er:

- Innehåll från Azure PowerShell (AzureRM): https://docs.microsoft.com/powershell/azure/
- Innehåll från Azure PowerShell (ASM): https://docs.microsoft.com/powershell/azure/_servicemanagement_
- Innehåll från Azure Active Directory (AzureAD) PowerShell: https://docs.microsoft.com/powershell/azure/_active directory_
- Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_
- Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_
- Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_

När du använder dessa URL:er kommer du att omdirigeras till den senaste versionen av innehållet. På detta sätt behöver du inte ange en versionsmoniker. Och du behöver inte heller ha länkar till konceptuellt innehåll som måste uppdateras när versionen ändras.

För att skapa korrekt länk söker du upp sidan du vill länka till i din webbläsare och kopierar URL-adressen.
Ta sedan bort https://docs.microsoft.com och informationen om nationella inställningar.

När du länkar från en innehållsförteckning måste du använda den fullständiga URL:en utan språkinformationen.

Markdown-exempel:

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
