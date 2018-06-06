---
title: Använda Markdown för att skriva i Docs
description: Den här artikeln innehåller grundläggande information och referensinformation för Markdown-språket som används för att skriva artiklar på docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 07/13/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 041398361aef90c44bdf3a0dad4aaa2d40a38289
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469956"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="7932a-103">Använda Markdown för att skriva i Docs</span><span class="sxs-lookup"><span data-stu-id="7932a-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="7932a-104">Docs.microsoft.com-artiklar skrivs i ett förenklat märkspråk som heter [Markdown](https://daringfireball.net/projects/markdown/) vilket är lätt att läsa och lätt att lära sig.</span><span class="sxs-lookup"><span data-stu-id="7932a-104">Docs.microsoft.com articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="7932a-105">På grund av detta har det snabbt blivit en industristandard.</span><span class="sxs-lookup"><span data-stu-id="7932a-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="7932a-106">Eftersom Docs-innehåll lagras på GitHub används en överordnad uppsättning av Markdown som kallas [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) som ger ytterligare funktioner för vanliga formateringsbehov.</span><span class="sxs-lookup"><span data-stu-id="7932a-106">Because Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="7932a-107">Open Publishing Services (OPS) implementerar dessutom Markdig Markdown Parser.</span><span class="sxs-lookup"><span data-stu-id="7932a-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="7932a-108">Markdig är starkt kompatibelt med GitHub Flavored Markdown (GFM), vilket möjliggör Docs-specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="7932a-108">Markdig is highly compatible with GitHub Flavored Markdown (GFM), adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="7932a-109">Markdig är en snabb, kraftfull, CommonMark-kompatibel, utökningsbar Markdown-processor för .NET.</span><span class="sxs-lookup"><span data-stu-id="7932a-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="7932a-110">Bättre communitysupport</span><span class="sxs-lookup"><span data-stu-id="7932a-110">Better community support</span></span>
* <span data-ttu-id="7932a-111">Bättre standardsupport</span><span class="sxs-lookup"><span data-stu-id="7932a-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="7932a-112">Grunder för Markdown</span><span class="sxs-lookup"><span data-stu-id="7932a-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="7932a-113">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="7932a-113">Headings</span></span>

<span data-ttu-id="7932a-114">Använd fyrkantstecknet (#) för att skapa en rubrik:</span><span class="sxs-lookup"><span data-stu-id="7932a-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="7932a-115">Fet och kursiv stil</span><span class="sxs-lookup"><span data-stu-id="7932a-115">Bold and italic text</span></span>

<span data-ttu-id="7932a-116">Använd två asterisker runt textsträngen för att formatera text som **fet**:</span><span class="sxs-lookup"><span data-stu-id="7932a-116">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
    This text is **bold**.
```

<span data-ttu-id="7932a-117">Använd en asterisk runt textsträngen för att formatera text som *kursiv*:</span><span class="sxs-lookup"><span data-stu-id="7932a-117">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
    This text is *italic*.
```

<span data-ttu-id="7932a-118">Använd tre asterisker runt textsträngen för att formatera text som både ***fet och kursiv***:</span><span class="sxs-lookup"><span data-stu-id="7932a-118">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="7932a-119">Listor</span><span class="sxs-lookup"><span data-stu-id="7932a-119">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="7932a-120">Osorterad lista</span><span class="sxs-lookup"><span data-stu-id="7932a-120">Unordered list</span></span>

<span data-ttu-id="7932a-121">Du kan använda asterisker eller tankstreck för att formatera en punktlista eller en osorterad lista.</span><span class="sxs-lookup"><span data-stu-id="7932a-121">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="7932a-122">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="7932a-122">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="7932a-123">återges som:</span><span class="sxs-lookup"><span data-stu-id="7932a-123">will be rendered as:</span></span>

- <span data-ttu-id="7932a-124">Listobjekt 1</span><span class="sxs-lookup"><span data-stu-id="7932a-124">List item 1</span></span>
- <span data-ttu-id="7932a-125">Listobjekt 2</span><span class="sxs-lookup"><span data-stu-id="7932a-125">List item 2</span></span>
- <span data-ttu-id="7932a-126">Listobjekt 3</span><span class="sxs-lookup"><span data-stu-id="7932a-126">List item 3</span></span>

<span data-ttu-id="7932a-127">Om du vill bädda in en lista i en annan lista skapar du ett indrag före den underordnade listans objekt.</span><span class="sxs-lookup"><span data-stu-id="7932a-127">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="7932a-128">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="7932a-128">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="7932a-129">återges som:</span><span class="sxs-lookup"><span data-stu-id="7932a-129">will be rendered as:</span></span>

- <span data-ttu-id="7932a-130">Listobjekt 1</span><span class="sxs-lookup"><span data-stu-id="7932a-130">List item 1</span></span>
  - <span data-ttu-id="7932a-131">Listobjekt A</span><span class="sxs-lookup"><span data-stu-id="7932a-131">List item A</span></span>
  - <span data-ttu-id="7932a-132">Listobjekt B</span><span class="sxs-lookup"><span data-stu-id="7932a-132">List item B</span></span>
- <span data-ttu-id="7932a-133">Listobjekt 2</span><span class="sxs-lookup"><span data-stu-id="7932a-133">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="7932a-134">Ordnad lista</span><span class="sxs-lookup"><span data-stu-id="7932a-134">Ordered list</span></span>

<span data-ttu-id="7932a-135">Du kan använda motsvarande siffror för att formatera en ordnad/stegvis lista.</span><span class="sxs-lookup"><span data-stu-id="7932a-135">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="7932a-136">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="7932a-136">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="7932a-137">återges som:</span><span class="sxs-lookup"><span data-stu-id="7932a-137">will be rendered as:</span></span>

1. <span data-ttu-id="7932a-138">Första instruktionen</span><span class="sxs-lookup"><span data-stu-id="7932a-138">First instruction</span></span>
2. <span data-ttu-id="7932a-139">Andra instruktionen</span><span class="sxs-lookup"><span data-stu-id="7932a-139">Second instruction</span></span>
3. <span data-ttu-id="7932a-140">Tredje instruktionen</span><span class="sxs-lookup"><span data-stu-id="7932a-140">Third instruction</span></span>

<span data-ttu-id="7932a-141">Om du vill bädda in en lista i en annan lista skapar du ett indrag före den underordnade listans objekt.</span><span class="sxs-lookup"><span data-stu-id="7932a-141">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="7932a-142">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="7932a-142">For example, the following Markdown:</span></span>

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="7932a-143">återges som:</span><span class="sxs-lookup"><span data-stu-id="7932a-143">will be rendered as:</span></span>

1. <span data-ttu-id="7932a-144">Första instruktionen</span><span class="sxs-lookup"><span data-stu-id="7932a-144">First instruction</span></span>
    1. <span data-ttu-id="7932a-145">Underinstruktion</span><span class="sxs-lookup"><span data-stu-id="7932a-145">Sub-instruction</span></span>
    2. <span data-ttu-id="7932a-146">Underinstruktion</span><span class="sxs-lookup"><span data-stu-id="7932a-146">Sub-instruction</span></span>
2. <span data-ttu-id="7932a-147">Andra instruktionen</span><span class="sxs-lookup"><span data-stu-id="7932a-147">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="7932a-148">Tabeller</span><span class="sxs-lookup"><span data-stu-id="7932a-148">Tables</span></span>

<span data-ttu-id="7932a-149">Tabeller är inte del av stommen i Markdown-specifikationerna, men de stöds av GFM.</span><span class="sxs-lookup"><span data-stu-id="7932a-149">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="7932a-150">Du kan skapa tabeller med hjälp av tecknen lodrätt streck (|) och bindestreck (-).</span><span class="sxs-lookup"><span data-stu-id="7932a-150">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="7932a-151">Bindestreck skapar varje kolumnrubrik medan lodräta streck separerar varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="7932a-151">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="7932a-152">Inkludera ett blankstreck framför tabellen så att den renderas korrekt.</span><span class="sxs-lookup"><span data-stu-id="7932a-152">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="7932a-153">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="7932a-153">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="7932a-154">återges som:</span><span class="sxs-lookup"><span data-stu-id="7932a-154">will be rendered as:</span></span>

| <span data-ttu-id="7932a-155">Roligt</span><span class="sxs-lookup"><span data-stu-id="7932a-155">Fun</span></span>                  | <span data-ttu-id="7932a-156">Med</span><span class="sxs-lookup"><span data-stu-id="7932a-156">With</span></span>                 | <span data-ttu-id="7932a-157">Tabeller</span><span class="sxs-lookup"><span data-stu-id="7932a-157">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="7932a-158">vänsterjusterad kolumn</span><span class="sxs-lookup"><span data-stu-id="7932a-158">left-aligned column</span></span>  | <span data-ttu-id="7932a-159">högerjusterad kolumn</span><span class="sxs-lookup"><span data-stu-id="7932a-159">right-aligned column</span></span> | <span data-ttu-id="7932a-160">centrerad kolumn</span><span class="sxs-lookup"><span data-stu-id="7932a-160">centered column</span></span> |
| <span data-ttu-id="7932a-161">$100</span><span class="sxs-lookup"><span data-stu-id="7932a-161">$100</span></span>                 | <span data-ttu-id="7932a-162">$100</span><span class="sxs-lookup"><span data-stu-id="7932a-162">$100</span></span>                 | <span data-ttu-id="7932a-163">$100</span><span class="sxs-lookup"><span data-stu-id="7932a-163">$100</span></span>            |
| <span data-ttu-id="7932a-164">$10</span><span class="sxs-lookup"><span data-stu-id="7932a-164">$10</span></span>                  | <span data-ttu-id="7932a-165">$10</span><span class="sxs-lookup"><span data-stu-id="7932a-165">$10</span></span>                  | <span data-ttu-id="7932a-166">$10</span><span class="sxs-lookup"><span data-stu-id="7932a-166">$10</span></span>             |
| <span data-ttu-id="7932a-167">$1</span><span class="sxs-lookup"><span data-stu-id="7932a-167">$1</span></span>                   | <span data-ttu-id="7932a-168">$1</span><span class="sxs-lookup"><span data-stu-id="7932a-168">$1</span></span>                   | <span data-ttu-id="7932a-169">$1</span><span class="sxs-lookup"><span data-stu-id="7932a-169">$1</span></span>              |

<span data-ttu-id="7932a-170">Mer information om att skapa tabeller finns här:</span><span class="sxs-lookup"><span data-stu-id="7932a-170">For more information on creating tables, see:</span></span>

- <span data-ttu-id="7932a-171">[Tabellhanteringsfunktionen](#table-wrapping) i Markdig kan vara användbar vid formatering av breda tabeller</span><span class="sxs-lookup"><span data-stu-id="7932a-171">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables</span></span>
- <span data-ttu-id="7932a-172">GitHubs [Organisera information med tabeller](https://help.github.com/articles/organizing-information-with-tables/)</span><span class="sxs-lookup"><span data-stu-id="7932a-172">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)</span></span>
- <span data-ttu-id="7932a-173">Webbappen [Markdown-tabellgenerator](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="7932a-173">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app</span></span>
- [<span data-ttu-id="7932a-174">Adam Pritchards lathund för Markdown</span><span class="sxs-lookup"><span data-stu-id="7932a-174">Adam Pritchard's Markdown Cheatsheet</span></span>](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)
- [<span data-ttu-id="7932a-175">Michel Fortins extra om Markdown</span><span class="sxs-lookup"><span data-stu-id="7932a-175">Michel Fortin's Markdown Extra</span></span>](https://michelf.ca/projects/php-markdown/extra/#table)
- [<span data-ttu-id="7932a-176">Konvertera HTML-tabeller till Markdown</span><span class="sxs-lookup"><span data-stu-id="7932a-176">Convert HTML tables to Markdown</span></span>](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a><span data-ttu-id="7932a-177">Länkar</span><span class="sxs-lookup"><span data-stu-id="7932a-177">Links</span></span>

<span data-ttu-id="7932a-178">Markdown-syntaxen för en intern länk består av en `[link text]`-del, som består av texten som länkas, följt av `(file-name.md)`-delen, vilket är den länkade webbadressen eller filnamnet:</span><span class="sxs-lookup"><span data-stu-id="7932a-178">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="7932a-179">För mer information om länkar, se:</span><span class="sxs-lookup"><span data-stu-id="7932a-179">For more information on linking, see:</span></span>

- <span data-ttu-id="7932a-180">[Markdown-syntaxguiden](https://daringfireball.net/projects/markdown/syntax#link) för information om Markdowns stöd för baslänkning.</span><span class="sxs-lookup"><span data-stu-id="7932a-180">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="7932a-181">Avsnittet [Länkar](how-to-write-links.md) i den här anvisningen för information om mer länkningssyntax som Markdig erbjuder.</span><span class="sxs-lookup"><span data-stu-id="7932a-181">The [Links](how-to-write-links.md) section of this guide for details on additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="7932a-182">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="7932a-182">Code snippets</span></span>

<span data-ttu-id="7932a-183">Markdown stöder placering av interna kodfragment i en mening samt avskilda kodfragment mellan meningar.</span><span class="sxs-lookup"><span data-stu-id="7932a-183">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="7932a-184">Mer information finns här:</span><span class="sxs-lookup"><span data-stu-id="7932a-184">For details, see:</span></span>

- [<span data-ttu-id="7932a-185">Markdowns inbyggda stöd för kodblock</span><span class="sxs-lookup"><span data-stu-id="7932a-185">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="7932a-186">GFM:s stöd för avskild kod och syntaxmarkering</span><span class="sxs-lookup"><span data-stu-id="7932a-186">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="7932a-187">Genom att skilja kodfragment är det lätt att markera syntaxen för dessa.</span><span class="sxs-lookup"><span data-stu-id="7932a-187">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="7932a-188">Det allmänna formatet för skilda kodblock är:</span><span class="sxs-lookup"><span data-stu-id="7932a-188">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="7932a-189">Alias efter de tre första accenttecknen'\`' definierar vilken syntaxmarkering som ska användas.</span><span class="sxs-lookup"><span data-stu-id="7932a-189">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="7932a-190">Följande är en lista över vanliga programmeringsspråk i Docs-innehåll och motsvarande etikett:</span><span class="sxs-lookup"><span data-stu-id="7932a-190">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="7932a-191">Dessa språk har support för eget namn och de flesta har språkmarkering.</span><span class="sxs-lookup"><span data-stu-id="7932a-191">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="7932a-192">Namn</span><span class="sxs-lookup"><span data-stu-id="7932a-192">Name</span></span>|<span data-ttu-id="7932a-193">Markdown-etikett</span><span class="sxs-lookup"><span data-stu-id="7932a-193">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="7932a-194">.NET Console</span><span class="sxs-lookup"><span data-stu-id="7932a-194">.NET Console</span></span>|<span data-ttu-id="7932a-195">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="7932a-195">dotnetcli</span></span>|
|<span data-ttu-id="7932a-196">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="7932a-196">ASP.NET (C#)</span></span>|<span data-ttu-id="7932a-197">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="7932a-197">aspx-csharp</span></span>|
|<span data-ttu-id="7932a-198">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="7932a-198">ASP.NET (VB)</span></span>|<span data-ttu-id="7932a-199">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="7932a-199">aspx-vb</span></span>|
|<span data-ttu-id="7932a-200">AzCopy</span><span class="sxs-lookup"><span data-stu-id="7932a-200">AzCopy</span></span>|<span data-ttu-id="7932a-201">azcopy</span><span class="sxs-lookup"><span data-stu-id="7932a-201">azcopy</span></span>|
|<span data-ttu-id="7932a-202">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="7932a-202">Azure CLI</span></span>|<span data-ttu-id="7932a-203">azurecli</span><span class="sxs-lookup"><span data-stu-id="7932a-203">azurecli</span></span>|
|<span data-ttu-id="7932a-204">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="7932a-204">Azure PowerShell</span></span>|<span data-ttu-id="7932a-205">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="7932a-205">azurepowershell</span></span>|
|<span data-ttu-id="7932a-206">C++</span><span class="sxs-lookup"><span data-stu-id="7932a-206">C++</span></span>|<span data-ttu-id="7932a-207">cpp</span><span class="sxs-lookup"><span data-stu-id="7932a-207">cpp</span></span>|
|<span data-ttu-id="7932a-208">C++/CX</span><span class="sxs-lookup"><span data-stu-id="7932a-208">C++/CX</span></span>|<span data-ttu-id="7932a-209">cppcx</span><span class="sxs-lookup"><span data-stu-id="7932a-209">cppcx</span></span>|
|<span data-ttu-id="7932a-210">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="7932a-210">C++/WinRT</span></span>|<span data-ttu-id="7932a-211">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="7932a-211">cppwinrt</span></span>|
|<span data-ttu-id="7932a-212">C#</span><span class="sxs-lookup"><span data-stu-id="7932a-212">C#</span></span>|<span data-ttu-id="7932a-213">csharp</span><span class="sxs-lookup"><span data-stu-id="7932a-213">csharp</span></span>|
|<span data-ttu-id="7932a-214">CSHTML</span><span class="sxs-lookup"><span data-stu-id="7932a-214">CSHTML</span></span>|<span data-ttu-id="7932a-215">cshtml</span><span class="sxs-lookup"><span data-stu-id="7932a-215">cshtml</span></span>|
|<span data-ttu-id="7932a-216">DAX</span><span class="sxs-lookup"><span data-stu-id="7932a-216">DAX</span></span>|<span data-ttu-id="7932a-217">dax</span><span class="sxs-lookup"><span data-stu-id="7932a-217">dax</span></span>|
|<span data-ttu-id="7932a-218">F#</span><span class="sxs-lookup"><span data-stu-id="7932a-218">F#</span></span>|<span data-ttu-id="7932a-219">fsharp</span><span class="sxs-lookup"><span data-stu-id="7932a-219">fsharp</span></span>|
|<span data-ttu-id="7932a-220">Go</span><span class="sxs-lookup"><span data-stu-id="7932a-220">Go</span></span>|<span data-ttu-id="7932a-221">go</span><span class="sxs-lookup"><span data-stu-id="7932a-221">go</span></span>|
|<span data-ttu-id="7932a-222">HTML</span><span class="sxs-lookup"><span data-stu-id="7932a-222">HTML</span></span>|<span data-ttu-id="7932a-223">html</span><span class="sxs-lookup"><span data-stu-id="7932a-223">html</span></span>|
|<span data-ttu-id="7932a-224">HTTP</span><span class="sxs-lookup"><span data-stu-id="7932a-224">HTTP</span></span>|<span data-ttu-id="7932a-225">http</span><span class="sxs-lookup"><span data-stu-id="7932a-225">http</span></span>|
|<span data-ttu-id="7932a-226">Java</span><span class="sxs-lookup"><span data-stu-id="7932a-226">Java</span></span>|<span data-ttu-id="7932a-227">java</span><span class="sxs-lookup"><span data-stu-id="7932a-227">java</span></span>|
|<span data-ttu-id="7932a-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="7932a-228">JavaScript</span></span>|<span data-ttu-id="7932a-229">javascript</span><span class="sxs-lookup"><span data-stu-id="7932a-229">javascript</span></span>|
|<span data-ttu-id="7932a-230">JSON</span><span class="sxs-lookup"><span data-stu-id="7932a-230">JSON</span></span>|<span data-ttu-id="7932a-231">json</span><span class="sxs-lookup"><span data-stu-id="7932a-231">json</span></span>|
|<span data-ttu-id="7932a-232">Markdown</span><span class="sxs-lookup"><span data-stu-id="7932a-232">Markdown</span></span>|<span data-ttu-id="7932a-233">md</span><span class="sxs-lookup"><span data-stu-id="7932a-233">md</span></span>|
|<span data-ttu-id="7932a-234">NodeJS</span><span class="sxs-lookup"><span data-stu-id="7932a-234">NodeJS</span></span>|<span data-ttu-id="7932a-235">nodejs</span><span class="sxs-lookup"><span data-stu-id="7932a-235">nodejs</span></span>|
|<span data-ttu-id="7932a-236">Objective-C</span><span class="sxs-lookup"><span data-stu-id="7932a-236">Objective-C</span></span>|<span data-ttu-id="7932a-237">objc</span><span class="sxs-lookup"><span data-stu-id="7932a-237">objc</span></span>|
|<span data-ttu-id="7932a-238">OData</span><span class="sxs-lookup"><span data-stu-id="7932a-238">OData</span></span>|<span data-ttu-id="7932a-239">odata</span><span class="sxs-lookup"><span data-stu-id="7932a-239">odata</span></span>|
|<span data-ttu-id="7932a-240">PHP</span><span class="sxs-lookup"><span data-stu-id="7932a-240">PHP</span></span>|<span data-ttu-id="7932a-241">php</span><span class="sxs-lookup"><span data-stu-id="7932a-241">php</span></span>|
|<span data-ttu-id="7932a-242">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="7932a-242">Power Apps Formula</span></span>|<span data-ttu-id="7932a-243">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="7932a-243">powerappsfl</span></span>|
|<span data-ttu-id="7932a-244">PowerShell</span><span class="sxs-lookup"><span data-stu-id="7932a-244">PowerShell</span></span>|<span data-ttu-id="7932a-245">powershell</span><span class="sxs-lookup"><span data-stu-id="7932a-245">powershell</span></span>|
|<span data-ttu-id="7932a-246">Python</span><span class="sxs-lookup"><span data-stu-id="7932a-246">Python</span></span>|<span data-ttu-id="7932a-247">python</span><span class="sxs-lookup"><span data-stu-id="7932a-247">python</span></span>|
|<span data-ttu-id="7932a-248">Q#</span><span class="sxs-lookup"><span data-stu-id="7932a-248">Q#</span></span>|<span data-ttu-id="7932a-249">qsharp</span><span class="sxs-lookup"><span data-stu-id="7932a-249">qsharp</span></span>|
|<span data-ttu-id="7932a-250">Ruby</span><span class="sxs-lookup"><span data-stu-id="7932a-250">Ruby</span></span>|<span data-ttu-id="7932a-251">ruby</span><span class="sxs-lookup"><span data-stu-id="7932a-251">ruby</span></span>|
|<span data-ttu-id="7932a-252">SQL</span><span class="sxs-lookup"><span data-stu-id="7932a-252">SQL</span></span>|<span data-ttu-id="7932a-253">sql</span><span class="sxs-lookup"><span data-stu-id="7932a-253">sql</span></span>|
|<span data-ttu-id="7932a-254">Swift</span><span class="sxs-lookup"><span data-stu-id="7932a-254">Swift</span></span>|<span data-ttu-id="7932a-255">swift</span><span class="sxs-lookup"><span data-stu-id="7932a-255">swift</span></span>|
|<span data-ttu-id="7932a-256">TypeScript</span><span class="sxs-lookup"><span data-stu-id="7932a-256">TypeScript</span></span>|<span data-ttu-id="7932a-257">typescript</span><span class="sxs-lookup"><span data-stu-id="7932a-257">typescript</span></span>|
|<span data-ttu-id="7932a-258">VB</span><span class="sxs-lookup"><span data-stu-id="7932a-258">VB</span></span>|<span data-ttu-id="7932a-259">vb</span><span class="sxs-lookup"><span data-stu-id="7932a-259">vb</span></span>|
|<span data-ttu-id="7932a-260">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="7932a-260">VSTS CLI</span></span>|<span data-ttu-id="7932a-261">vstscli</span><span class="sxs-lookup"><span data-stu-id="7932a-261">vstscli</span></span>|
|<span data-ttu-id="7932a-262">XAML</span><span class="sxs-lookup"><span data-stu-id="7932a-262">XAML</span></span>|<span data-ttu-id="7932a-263">xaml</span><span class="sxs-lookup"><span data-stu-id="7932a-263">xaml</span></span>|
|<span data-ttu-id="7932a-264">XML</span><span class="sxs-lookup"><span data-stu-id="7932a-264">XML</span></span>|<span data-ttu-id="7932a-265">xml</span><span class="sxs-lookup"><span data-stu-id="7932a-265">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="7932a-266">Exempel: C\#</span><span class="sxs-lookup"><span data-stu-id="7932a-266">Example: C\#</span></span>

<span data-ttu-id="7932a-267">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="7932a-267">__Markdown__</span></span>

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

<span data-ttu-id="7932a-268">__Rendera__</span><span class="sxs-lookup"><span data-stu-id="7932a-268">__Render__</span></span>

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a><span data-ttu-id="7932a-269">Exempel: SQL</span><span class="sxs-lookup"><span data-stu-id="7932a-269">Example: SQL</span></span>

<span data-ttu-id="7932a-270">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="7932a-270">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="7932a-271">__Rendera__</span><span class="sxs-lookup"><span data-stu-id="7932a-271">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="7932a-272">OPS-anpassade Markdown-förlängningar</span><span class="sxs-lookup"><span data-stu-id="7932a-272">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="7932a-273">Open Publishing Services (OPS) implementerar Markdig Parser för Markdown, som är mycket kompatibel med GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="7932a-273">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="7932a-274">Markdig lägger till vissa ytterligare funktioner via Markdown-tillägg.</span><span class="sxs-lookup"><span data-stu-id="7932a-274">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="7932a-275">Utvalda artiklar från den fullständiga OPS-redigeringsguiden ingår till exempel i den här handboken som referens.</span><span class="sxs-lookup"><span data-stu-id="7932a-275">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="7932a-276">(Se till exempel ”Markdig- och Markdown-tillägg” och ”Kodfragment” i innehållsförteckningen.)</span><span class="sxs-lookup"><span data-stu-id="7932a-276">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="7932a-277">Docs-artiklar använder GFM för de flesta formerna av artikelformatering, som stycken, länkar, listor och rubriker.</span><span class="sxs-lookup"><span data-stu-id="7932a-277">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="7932a-278">För en djupare formatering kan artiklar använda Markdig-funktioner som:</span><span class="sxs-lookup"><span data-stu-id="7932a-278">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="7932a-279">Anteckningsblock</span><span class="sxs-lookup"><span data-stu-id="7932a-279">Note blocks</span></span>
- <span data-ttu-id="7932a-280">Inkluderar</span><span class="sxs-lookup"><span data-stu-id="7932a-280">Includes</span></span>
- <span data-ttu-id="7932a-281">Väljare</span><span class="sxs-lookup"><span data-stu-id="7932a-281">Selectors</span></span>
- <span data-ttu-id="7932a-282">Inbäddade videoklipp</span><span class="sxs-lookup"><span data-stu-id="7932a-282">Embedded videos</span></span>
- <span data-ttu-id="7932a-283">Kodfragment/-exempel</span><span class="sxs-lookup"><span data-stu-id="7932a-283">Code snippets/samples</span></span>

<span data-ttu-id="7932a-284">För en fullständig lista, se ”Markdig- och Markdown-tillägg” och ”Kodfragment” i innehållsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="7932a-284">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="7932a-285">Anteckningsblock</span><span class="sxs-lookup"><span data-stu-id="7932a-285">Note blocks</span></span>

<span data-ttu-id="7932a-286">Du kan välja bland fyra typer av anteckningsblock för att markera specifikt innehåll:</span><span class="sxs-lookup"><span data-stu-id="7932a-286">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="7932a-287">OBS</span><span class="sxs-lookup"><span data-stu-id="7932a-287">NOTE</span></span>
- <span data-ttu-id="7932a-288">VARNING</span><span class="sxs-lookup"><span data-stu-id="7932a-288">WARNING</span></span>
- <span data-ttu-id="7932a-289">TIPS</span><span class="sxs-lookup"><span data-stu-id="7932a-289">TIP</span></span>
- <span data-ttu-id="7932a-290">VIKTIGT</span><span class="sxs-lookup"><span data-stu-id="7932a-290">IMPORTANT</span></span>

<span data-ttu-id="7932a-291">Som regel bör anteckningsblock användas sparsamt eftersom de kan vara störande.</span><span class="sxs-lookup"><span data-stu-id="7932a-291">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="7932a-292">Anteckningsblock stöder kodblock, bilder, listor och länkar, men bör vara så enkla som möjligt.</span><span class="sxs-lookup"><span data-stu-id="7932a-292">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="7932a-293">Inkluderar</span><span class="sxs-lookup"><span data-stu-id="7932a-293">Includes</span></span>

<span data-ttu-id="7932a-294">När du har en text- eller bildfil som kan återanvändas och som måste ingå i artikelfiler kan du använda en referens som "inkluderar" filen via funktionen inkludera fil i Markdig.</span><span class="sxs-lookup"><span data-stu-id="7932a-294">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="7932a-295">Funktionen ger OPS en instruktion att inkludera den angivna filen i din artikelfil när den byggs, vilket gör den till en del av den publicerade artikeln.</span><span class="sxs-lookup"><span data-stu-id="7932a-295">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="7932a-296">Det finns tre typer av inkluderingar som hjälper dig att återanvända innehåll:</span><span class="sxs-lookup"><span data-stu-id="7932a-296">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="7932a-297">Intern – Återanvänd en vanlig textsträng i en annan mening.</span><span class="sxs-lookup"><span data-stu-id="7932a-297">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="7932a-298">Block – Återanvänd en hel Markdown-fil som ett block som bäddas in i en del av artikeln.</span><span class="sxs-lookup"><span data-stu-id="7932a-298">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="7932a-299">Bild – Detta är standardsättet att inkludera bilder i Docs.</span><span class="sxs-lookup"><span data-stu-id="7932a-299">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="7932a-300">Interna inkluderingar och blockinkluderingar är bara enkla Markdown-filer (.md).</span><span class="sxs-lookup"><span data-stu-id="7932a-300">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="7932a-301">De kan innehålla alla sorters giltiga Markdowns.</span><span class="sxs-lookup"><span data-stu-id="7932a-301">It can contain any valid Markdown.</span></span> <span data-ttu-id="7932a-302">Alla inkluderingsfiler i Markdown bör placeras i en [gemensam`/includes` underkatalog](git-github-fundamentals.md#includes-subdirectory) i lagringsplatsens rot.</span><span class="sxs-lookup"><span data-stu-id="7932a-302">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="7932a-303">När artikeln publiceras integreras den inkluderade filen sömlöst i den publicerade artikeln.</span><span class="sxs-lookup"><span data-stu-id="7932a-303">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="7932a-304">Här följer krav och överväganden för inkluderingar:</span><span class="sxs-lookup"><span data-stu-id="7932a-304">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="7932a-305">Använd inkludera när du vill att samma text ska visas i flera artiklar.</span><span class="sxs-lookup"><span data-stu-id="7932a-305">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="7932a-306">Använd blockinkluderingar för stora mängder innehåll – ett stycke eller två, en delad procedur eller ett delat avsnitt.</span><span class="sxs-lookup"><span data-stu-id="7932a-306">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="7932a-307">Använd dem inte för mindre än en mening.</span><span class="sxs-lookup"><span data-stu-id="7932a-307">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="7932a-308">Inkluderat innehåll återges inte i den renderade vyn för din artikel i GitHub eftersom de använder Markdig-tillägg.</span><span class="sxs-lookup"><span data-stu-id="7932a-308">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="7932a-309">De återges först efter publiceringen.</span><span class="sxs-lookup"><span data-stu-id="7932a-309">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="7932a-310">Kontrollera att all text i en inkludering är skriven i fullständiga meningar eller satser som inte är beroende av föregående eller efterföljande text i artikeln som använder den inkluderade texten.</span><span class="sxs-lookup"><span data-stu-id="7932a-310">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="7932a-311">Om du hoppar över detta steg kan en sträng som inte kan översättas skapas, vilket stör den lokaliserade upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="7932a-311">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="7932a-312">Bädda inte in inkluderingar med andra inkluderingar.</span><span class="sxs-lookup"><span data-stu-id="7932a-312">Don't embed includes within other includes.</span></span> <span data-ttu-id="7932a-313">De stöds inte.</span><span class="sxs-lookup"><span data-stu-id="7932a-313">They are not supported.</span></span>
- <span data-ttu-id="7932a-314">Placera mediefiler i en mediemapp som är specifik för inkluderingsunderkatalogen – till exempel, `<repo>`/inkluderingar/mediamapp.</span><span class="sxs-lookup"><span data-stu-id="7932a-314">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="7932a-315">Mediekatalogen bör inte innehålla några bilder i sin rot.</span><span class="sxs-lookup"><span data-stu-id="7932a-315">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="7932a-316">Om inkluderingen inte har bilder behövs inte en motsvarande mediekatalog.</span><span class="sxs-lookup"><span data-stu-id="7932a-316">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="7932a-317">Precis som med vanliga artiklar bör du inte dela media mellan inkluderingsfiler.</span><span class="sxs-lookup"><span data-stu-id="7932a-317">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="7932a-318">Använd en särskild fil med ett unikt namn för varje inkludering och artikel.</span><span class="sxs-lookup"><span data-stu-id="7932a-318">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="7932a-319">Lagra mediefilen i mediemappen som associeras med inkluderingen.</span><span class="sxs-lookup"><span data-stu-id="7932a-319">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="7932a-320">Använd inte en inkludering som det enda innehållet i en artikel.</span><span class="sxs-lookup"><span data-stu-id="7932a-320">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="7932a-321">Inkluderingar är avsedda att komplettera övrigt innehåll i en artikel.</span><span class="sxs-lookup"><span data-stu-id="7932a-321">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="7932a-322">Väljare</span><span class="sxs-lookup"><span data-stu-id="7932a-322">Selectors</span></span>

<span data-ttu-id="7932a-323">Använd väljare i tekniska artiklar när du skriver olika versioner av samma artikel för att visa implementeringsskillnader för olika tekniker eller plattformar.</span><span class="sxs-lookup"><span data-stu-id="7932a-323">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="7932a-324">Detta gäller framför allt för innehåll vår plattform för mobilt innehåll för utvecklare.</span><span class="sxs-lookup"><span data-stu-id="7932a-324">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="7932a-325">Det finns för närvarande två typer av väljare i Markdig: en enkel väljare och en multiväljare.</span><span class="sxs-lookup"><span data-stu-id="7932a-325">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="7932a-326">Eftersom samma Markdown för väljare används i alla markerade artiklar rekommenderar vi att du placerar väljaren för en artikel i en inkludering.</span><span class="sxs-lookup"><span data-stu-id="7932a-326">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="7932a-327">Du kan sedan hänvisa till den inkluderingen i alla artiklar som använder samma väljare.</span><span class="sxs-lookup"><span data-stu-id="7932a-327">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="7932a-328">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="7932a-328">Code snippets</span></span>

<span data-ttu-id="7932a-329">Markdig har stöd för avancerad inkludering av kod i artiklar, tack vare kodfragmentstillägget.</span><span class="sxs-lookup"><span data-stu-id="7932a-329">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="7932a-330">Tillägget möjliggör avancerad rendering som bygger på GFM-funktioner som programmeringsspråkval och syntaxfärgning, samt användbara funktioner som:</span><span class="sxs-lookup"><span data-stu-id="7932a-330">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="7932a-331">Inkludering av centraliserade kodexempel/-fragment från externa lagringsplatser.</span><span class="sxs-lookup"><span data-stu-id="7932a-331">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="7932a-332">Användargränssnitt i flikar för att visa olika versioner av kodexempel i olika språk.</span><span class="sxs-lookup"><span data-stu-id="7932a-332">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="7932a-333">Information och felsökning</span><span class="sxs-lookup"><span data-stu-id="7932a-333">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="7932a-334">Alternativ text</span><span class="sxs-lookup"><span data-stu-id="7932a-334">Alt text</span></span>

<span data-ttu-id="7932a-335">Alternativ text som innehåller understreck återges inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="7932a-335">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="7932a-336">Till exempel, i stället för att använda detta:</span><span class="sxs-lookup"><span data-stu-id="7932a-336">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="7932a-337">Använd escape-tecken för understrecken, så här:</span><span class="sxs-lookup"><span data-stu-id="7932a-337">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="7932a-338">Apostrofer och citattecken</span><span class="sxs-lookup"><span data-stu-id="7932a-338">Apostrophes and quotation marks</span></span>

<span data-ttu-id="7932a-339">Om du kopierar från Word till en Markdown-redigerare kan texten innehålla ”smarta”(sneda) apostrofer eller citattecken.</span><span class="sxs-lookup"><span data-stu-id="7932a-339">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="7932a-340">Dessa måste vara kodade eller ändras till raka apostrofer eller citattecken.</span><span class="sxs-lookup"><span data-stu-id="7932a-340">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="7932a-341">Annars kan det se ut så här när filen publiceras: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="7932a-341">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="7932a-342">Så här skriver du ”smarta” skiljetecken:</span><span class="sxs-lookup"><span data-stu-id="7932a-342">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="7932a-343">Vänster citattecken: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="7932a-343">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="7932a-344">Höger citattecken: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="7932a-344">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="7932a-345">Höger, enkelt citattecken eller apostrof: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="7932a-345">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="7932a-346">Vänster, enkelt citattecken: `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="7932a-346">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="7932a-347">Vinkelparentes</span><span class="sxs-lookup"><span data-stu-id="7932a-347">Angle brackets</span></span>

<span data-ttu-id="7932a-348">Om du använder vinkelparenteser i texten (inte koden) – till exempel för att markera en platshållare – måste du skriva hakparenteserna i kod.</span><span class="sxs-lookup"><span data-stu-id="7932a-348">If you use angle brackets in text (not code) in your file--for example, to denote a placeholder--you need to manually encode the angle brackets.</span></span> <span data-ttu-id="7932a-349">Annars tror Markdown att det är en HTML-tagg.</span><span class="sxs-lookup"><span data-stu-id="7932a-349">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="7932a-350">Till exempel, koda `<script name>` som `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="7932a-350">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="7932a-351">Se även</span><span class="sxs-lookup"><span data-stu-id="7932a-351">See also</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="7932a-352">Markdown-resurser</span><span class="sxs-lookup"><span data-stu-id="7932a-352">Markdown resources</span></span>

- [<span data-ttu-id="7932a-353">Introduktion till Markdown</span><span class="sxs-lookup"><span data-stu-id="7932a-353">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="7932a-354">Docs Markdown lathund</span><span class="sxs-lookup"><span data-stu-id="7932a-354">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="7932a-355">Grunder för Markdown i GitHub</span><span class="sxs-lookup"><span data-stu-id="7932a-355">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
