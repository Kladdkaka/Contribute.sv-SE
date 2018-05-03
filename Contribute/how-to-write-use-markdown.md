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
ms.openlocfilehash: 96d00abc052c3b23ca62201dccdbe590a927e72d
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="6e852-103">Använda Markdown för att skriva i Docs</span><span class="sxs-lookup"><span data-stu-id="6e852-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="6e852-104">Docs.microsoft.com-artiklar skrivs i ett förenklat märkspråk som heter [Markdown](https://daringfireball.net/projects/markdown/) vilket är lätt att läsa och lätt att lära sig.</span><span class="sxs-lookup"><span data-stu-id="6e852-104">Docs.microsoft.com articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="6e852-105">På grund av detta har det snabbt blivit en industristandard.</span><span class="sxs-lookup"><span data-stu-id="6e852-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="6e852-106">Eftersom Docs-innehåll lagras på GitHub används en överordnad uppsättning av Markdown som kallas [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) som ger ytterligare funktioner för vanliga formateringsbehov.</span><span class="sxs-lookup"><span data-stu-id="6e852-106">Because Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="6e852-107">Open Publishing Services (OPS) implementerar dessutom DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="6e852-107">Additionally, Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="6e852-108">DFM är starkt kompatibelt med GitHub Flavored Markdown (GFM), vilket möjliggör Docs-specifika funktioner.</span><span class="sxs-lookup"><span data-stu-id="6e852-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), adding functionality to enable Docs-specific features.</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="6e852-109">Grunder för Markdown</span><span class="sxs-lookup"><span data-stu-id="6e852-109">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="6e852-110">Sidhuvud</span><span class="sxs-lookup"><span data-stu-id="6e852-110">Headings</span></span>

<span data-ttu-id="6e852-111">Använd fyrkantstecknet (#) för att skapa en rubrik:</span><span class="sxs-lookup"><span data-stu-id="6e852-111">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="6e852-112">Fet och kursiv stil</span><span class="sxs-lookup"><span data-stu-id="6e852-112">Bold and italic text</span></span>

<span data-ttu-id="6e852-113">Använd två asterisker runt textsträngen för att formatera text som **fet**:</span><span class="sxs-lookup"><span data-stu-id="6e852-113">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
    This text is **bold**.
```

<span data-ttu-id="6e852-114">Använd en asterisk runt textsträngen för att formatera text som *kursiv*:</span><span class="sxs-lookup"><span data-stu-id="6e852-114">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
    This text is *italic*.
```

<span data-ttu-id="6e852-115">Använd tre asterisker runt textsträngen för att formatera text som både ***fet och kursiv***:</span><span class="sxs-lookup"><span data-stu-id="6e852-115">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="6e852-116">Listor</span><span class="sxs-lookup"><span data-stu-id="6e852-116">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="6e852-117">Osorterad lista</span><span class="sxs-lookup"><span data-stu-id="6e852-117">Unordered list</span></span>

<span data-ttu-id="6e852-118">Du kan använda asterisker eller tankstreck för att formatera en punktlista eller en osorterad lista.</span><span class="sxs-lookup"><span data-stu-id="6e852-118">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="6e852-119">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="6e852-119">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="6e852-120">återges som:</span><span class="sxs-lookup"><span data-stu-id="6e852-120">will be rendered as:</span></span>

- <span data-ttu-id="6e852-121">Listobjekt 1</span><span class="sxs-lookup"><span data-stu-id="6e852-121">List item 1</span></span>
- <span data-ttu-id="6e852-122">Listobjekt 2</span><span class="sxs-lookup"><span data-stu-id="6e852-122">List item 2</span></span>
- <span data-ttu-id="6e852-123">Listobjekt 3</span><span class="sxs-lookup"><span data-stu-id="6e852-123">List item 3</span></span>

<span data-ttu-id="6e852-124">Om du vill bädda in en lista i en annan lista skapar du ett indrag före den underordnade listans objekt.</span><span class="sxs-lookup"><span data-stu-id="6e852-124">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="6e852-125">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="6e852-125">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="6e852-126">återges som:</span><span class="sxs-lookup"><span data-stu-id="6e852-126">will be rendered as:</span></span>

- <span data-ttu-id="6e852-127">Listobjekt 1</span><span class="sxs-lookup"><span data-stu-id="6e852-127">List item 1</span></span>
  - <span data-ttu-id="6e852-128">Listobjekt A</span><span class="sxs-lookup"><span data-stu-id="6e852-128">List item A</span></span>
  - <span data-ttu-id="6e852-129">Listobjekt B</span><span class="sxs-lookup"><span data-stu-id="6e852-129">List item B</span></span>
- <span data-ttu-id="6e852-130">Listobjekt 2</span><span class="sxs-lookup"><span data-stu-id="6e852-130">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="6e852-131">Ordnad lista</span><span class="sxs-lookup"><span data-stu-id="6e852-131">Ordered list</span></span>

<span data-ttu-id="6e852-132">Du kan använda motsvarande siffror för att formatera en ordnad/stegvis lista.</span><span class="sxs-lookup"><span data-stu-id="6e852-132">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="6e852-133">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="6e852-133">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="6e852-134">återges som:</span><span class="sxs-lookup"><span data-stu-id="6e852-134">will be rendered as:</span></span>

1. <span data-ttu-id="6e852-135">Första instruktionen</span><span class="sxs-lookup"><span data-stu-id="6e852-135">First instruction</span></span>
2. <span data-ttu-id="6e852-136">Andra instruktionen</span><span class="sxs-lookup"><span data-stu-id="6e852-136">Second instruction</span></span>
3. <span data-ttu-id="6e852-137">Tredje instruktionen</span><span class="sxs-lookup"><span data-stu-id="6e852-137">Third instruction</span></span>

<span data-ttu-id="6e852-138">Om du vill bädda in en lista i en annan lista skapar du ett indrag före den underordnade listans objekt.</span><span class="sxs-lookup"><span data-stu-id="6e852-138">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="6e852-139">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="6e852-139">For example, the following Markdown:</span></span>

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="6e852-140">återges som:</span><span class="sxs-lookup"><span data-stu-id="6e852-140">will be rendered as:</span></span>

1. <span data-ttu-id="6e852-141">Första instruktionen</span><span class="sxs-lookup"><span data-stu-id="6e852-141">First instruction</span></span>
    1. <span data-ttu-id="6e852-142">Underinstruktion</span><span class="sxs-lookup"><span data-stu-id="6e852-142">Sub-instruction</span></span>
    2. <span data-ttu-id="6e852-143">Underinstruktion</span><span class="sxs-lookup"><span data-stu-id="6e852-143">Sub-instruction</span></span>
2. <span data-ttu-id="6e852-144">Andra instruktionen</span><span class="sxs-lookup"><span data-stu-id="6e852-144">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="6e852-145">Tabeller</span><span class="sxs-lookup"><span data-stu-id="6e852-145">Tables</span></span>

<span data-ttu-id="6e852-146">Tabeller är inte del av stommen i Markdown-specifikationerna, men de stöds av GFM.</span><span class="sxs-lookup"><span data-stu-id="6e852-146">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="6e852-147">Du kan skapa tabeller med hjälp av tecknen lodrätt streck (|) och bindestreck (-).</span><span class="sxs-lookup"><span data-stu-id="6e852-147">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="6e852-148">Bindestreck skapar varje kolumnrubrik medan lodräta streck separerar varje kolumn.</span><span class="sxs-lookup"><span data-stu-id="6e852-148">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="6e852-149">Inkludera ett blankstreck framför tabellen så att den renderas korrekt.</span><span class="sxs-lookup"><span data-stu-id="6e852-149">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="6e852-150">Till exempel, följande Markdown:</span><span class="sxs-lookup"><span data-stu-id="6e852-150">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="6e852-151">återges som:</span><span class="sxs-lookup"><span data-stu-id="6e852-151">will be rendered as:</span></span>

| <span data-ttu-id="6e852-152">Roligt</span><span class="sxs-lookup"><span data-stu-id="6e852-152">Fun</span></span>                  | <span data-ttu-id="6e852-153">Med</span><span class="sxs-lookup"><span data-stu-id="6e852-153">With</span></span>                 | <span data-ttu-id="6e852-154">Tabeller</span><span class="sxs-lookup"><span data-stu-id="6e852-154">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="6e852-155">vänsterjusterad kolumn</span><span class="sxs-lookup"><span data-stu-id="6e852-155">left-aligned column</span></span>  | <span data-ttu-id="6e852-156">högerjusterad kolumn</span><span class="sxs-lookup"><span data-stu-id="6e852-156">right-aligned column</span></span> | <span data-ttu-id="6e852-157">centrerad kolumn</span><span class="sxs-lookup"><span data-stu-id="6e852-157">centered column</span></span> |
| <span data-ttu-id="6e852-158">$100</span><span class="sxs-lookup"><span data-stu-id="6e852-158">$100</span></span>                 | <span data-ttu-id="6e852-159">$100</span><span class="sxs-lookup"><span data-stu-id="6e852-159">$100</span></span>                 | <span data-ttu-id="6e852-160">$100</span><span class="sxs-lookup"><span data-stu-id="6e852-160">$100</span></span>            |
| <span data-ttu-id="6e852-161">$10</span><span class="sxs-lookup"><span data-stu-id="6e852-161">$10</span></span>                  | <span data-ttu-id="6e852-162">$10</span><span class="sxs-lookup"><span data-stu-id="6e852-162">$10</span></span>                  | <span data-ttu-id="6e852-163">$10</span><span class="sxs-lookup"><span data-stu-id="6e852-163">$10</span></span>             |
| <span data-ttu-id="6e852-164">$1</span><span class="sxs-lookup"><span data-stu-id="6e852-164">$1</span></span>                   | <span data-ttu-id="6e852-165">$1</span><span class="sxs-lookup"><span data-stu-id="6e852-165">$1</span></span>                   | <span data-ttu-id="6e852-166">$1</span><span class="sxs-lookup"><span data-stu-id="6e852-166">$1</span></span>              |

<span data-ttu-id="6e852-167">Mer information om att skapa tabeller finns här:</span><span class="sxs-lookup"><span data-stu-id="6e852-167">For more information on creating tables, see:</span></span>

- <span data-ttu-id="6e852-168">[Tabellhanteringsfunktionen](#table-wrapping) i DFM kan vara användbar vid formatering av breda tabeller</span><span class="sxs-lookup"><span data-stu-id="6e852-168">The DFM [table wrapping feature](#table-wrapping), which can help with formatting of wide tables</span></span>
- <span data-ttu-id="6e852-169">GitHubs [Organisera information med tabeller](https://help.github.com/articles/organizing-information-with-tables/)</span><span class="sxs-lookup"><span data-stu-id="6e852-169">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)</span></span>
- <span data-ttu-id="6e852-170">Webbappen [Markdown-tabellgenerator](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="6e852-170">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app</span></span>
- [<span data-ttu-id="6e852-171">Adam Pritchards lathund för Markdown</span><span class="sxs-lookup"><span data-stu-id="6e852-171">Adam Pritchard's Markdown Cheatsheet</span></span>](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)
- [<span data-ttu-id="6e852-172">Michel Fortins extra om Markdown</span><span class="sxs-lookup"><span data-stu-id="6e852-172">Michel Fortin's Markdown Extra</span></span>](https://michelf.ca/projects/php-markdown/extra/#table)
- [<span data-ttu-id="6e852-173">Konvertera HTML-tabeller till Markdown</span><span class="sxs-lookup"><span data-stu-id="6e852-173">Convert HTML tables to Markdown</span></span>](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a><span data-ttu-id="6e852-174">Länkar</span><span class="sxs-lookup"><span data-stu-id="6e852-174">Links</span></span>

<span data-ttu-id="6e852-175">Markdown-syntaxen för en intern länk består av en `[link text]`-del, som består av texten som länkas, följt av `(file-name.md)`-delen, vilket är den länkade webbadressen eller filnamnet:</span><span class="sxs-lookup"><span data-stu-id="6e852-175">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="6e852-176">För mer information om länkar, se:</span><span class="sxs-lookup"><span data-stu-id="6e852-176">For more information on linking, see:</span></span>

- <span data-ttu-id="6e852-177">[Markdown-syntaxguiden](https://daringfireball.net/projects/markdown/syntax#link) för information om Markdowns stöd för baslänkning.</span><span class="sxs-lookup"><span data-stu-id="6e852-177">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="6e852-178">Avsnittet [Länkar](how-to-write-links.md) i den här anvisningen för information om mer länkningssyntax som DFM erbjuder.</span><span class="sxs-lookup"><span data-stu-id="6e852-178">The [Links](how-to-write-links.md) section of this guide for details on additional linking syntax that DFM provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="6e852-179">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="6e852-179">Code snippets</span></span>

<span data-ttu-id="6e852-180">Markdown stöder placering av interna kodfragment i en mening samt avskilda kodfragment mellan meningar.</span><span class="sxs-lookup"><span data-stu-id="6e852-180">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="6e852-181">Mer information finns här:</span><span class="sxs-lookup"><span data-stu-id="6e852-181">For details, see:</span></span>

- [<span data-ttu-id="6e852-182">Markdowns inbyggda stöd för kodblock</span><span class="sxs-lookup"><span data-stu-id="6e852-182">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="6e852-183">GFM:s stöd för avskild kod och syntaxmarkering</span><span class="sxs-lookup"><span data-stu-id="6e852-183">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="6e852-184">Genom att skilja kodfragment är det lätt att markera syntaxen för dessa.</span><span class="sxs-lookup"><span data-stu-id="6e852-184">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="6e852-185">Det allmänna formatet för skilda kodblock är:</span><span class="sxs-lookup"><span data-stu-id="6e852-185">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="6e852-186">Alias efter de tre första accenttecknen'\`' definierar vilken syntaxmarkering som ska användas.</span><span class="sxs-lookup"><span data-stu-id="6e852-186">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="6e852-187">Följande är en lista över vanliga programmeringsspråk i Docs-innehåll och motsvarande etikett:</span><span class="sxs-lookup"><span data-stu-id="6e852-187">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="6e852-188">Dessa språk har support för eget namn och de flesta har språkmarkering.</span><span class="sxs-lookup"><span data-stu-id="6e852-188">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="6e852-189">Namn</span><span class="sxs-lookup"><span data-stu-id="6e852-189">Name</span></span>|<span data-ttu-id="6e852-190">Markdown-etikett</span><span class="sxs-lookup"><span data-stu-id="6e852-190">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="6e852-191">.NET Console</span><span class="sxs-lookup"><span data-stu-id="6e852-191">.NET Console</span></span>|<span data-ttu-id="6e852-192">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="6e852-192">dotnetcli</span></span>|
|<span data-ttu-id="6e852-193">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="6e852-193">ASP.NET (C#)</span></span>|<span data-ttu-id="6e852-194">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="6e852-194">aspx-csharp</span></span>|
|<span data-ttu-id="6e852-195">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="6e852-195">ASP.NET (VB)</span></span>|<span data-ttu-id="6e852-196">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="6e852-196">aspx-vb</span></span>|
|<span data-ttu-id="6e852-197">AzCopy</span><span class="sxs-lookup"><span data-stu-id="6e852-197">AzCopy</span></span>|<span data-ttu-id="6e852-198">azcopy</span><span class="sxs-lookup"><span data-stu-id="6e852-198">azcopy</span></span>|
|<span data-ttu-id="6e852-199">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="6e852-199">Azure CLI</span></span>|<span data-ttu-id="6e852-200">azurecli</span><span class="sxs-lookup"><span data-stu-id="6e852-200">azurecli</span></span>|
|<span data-ttu-id="6e852-201">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e852-201">Azure PowerShell</span></span>|<span data-ttu-id="6e852-202">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="6e852-202">azurepowershell</span></span>|
|<span data-ttu-id="6e852-203">C++</span><span class="sxs-lookup"><span data-stu-id="6e852-203">C++</span></span>|<span data-ttu-id="6e852-204">cpp</span><span class="sxs-lookup"><span data-stu-id="6e852-204">cpp</span></span>|
|<span data-ttu-id="6e852-205">C++/CX</span><span class="sxs-lookup"><span data-stu-id="6e852-205">C++/CX</span></span>|<span data-ttu-id="6e852-206">cppcx</span><span class="sxs-lookup"><span data-stu-id="6e852-206">cppcx</span></span>|
|<span data-ttu-id="6e852-207">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="6e852-207">C++/WinRT</span></span>|<span data-ttu-id="6e852-208">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="6e852-208">cppwinrt</span></span>|
|<span data-ttu-id="6e852-209">C#</span><span class="sxs-lookup"><span data-stu-id="6e852-209">C#</span></span>|<span data-ttu-id="6e852-210">csharp</span><span class="sxs-lookup"><span data-stu-id="6e852-210">csharp</span></span>|
|<span data-ttu-id="6e852-211">CSHTML</span><span class="sxs-lookup"><span data-stu-id="6e852-211">CSHTML</span></span>|<span data-ttu-id="6e852-212">cshtml</span><span class="sxs-lookup"><span data-stu-id="6e852-212">cshtml</span></span>|
|<span data-ttu-id="6e852-213">DAX</span><span class="sxs-lookup"><span data-stu-id="6e852-213">DAX</span></span>|<span data-ttu-id="6e852-214">dax</span><span class="sxs-lookup"><span data-stu-id="6e852-214">dax</span></span>|
|<span data-ttu-id="6e852-215">F#</span><span class="sxs-lookup"><span data-stu-id="6e852-215">F#</span></span>|<span data-ttu-id="6e852-216">fsharp</span><span class="sxs-lookup"><span data-stu-id="6e852-216">fsharp</span></span>|
|<span data-ttu-id="6e852-217">Go</span><span class="sxs-lookup"><span data-stu-id="6e852-217">Go</span></span>|<span data-ttu-id="6e852-218">go</span><span class="sxs-lookup"><span data-stu-id="6e852-218">go</span></span>|
|<span data-ttu-id="6e852-219">HTML</span><span class="sxs-lookup"><span data-stu-id="6e852-219">HTML</span></span>|<span data-ttu-id="6e852-220">html</span><span class="sxs-lookup"><span data-stu-id="6e852-220">html</span></span>|
|<span data-ttu-id="6e852-221">HTTP</span><span class="sxs-lookup"><span data-stu-id="6e852-221">HTTP</span></span>|<span data-ttu-id="6e852-222">http</span><span class="sxs-lookup"><span data-stu-id="6e852-222">http</span></span>|
|<span data-ttu-id="6e852-223">Java</span><span class="sxs-lookup"><span data-stu-id="6e852-223">Java</span></span>|<span data-ttu-id="6e852-224">java</span><span class="sxs-lookup"><span data-stu-id="6e852-224">java</span></span>|
|<span data-ttu-id="6e852-225">JavaScript</span><span class="sxs-lookup"><span data-stu-id="6e852-225">JavaScript</span></span>|<span data-ttu-id="6e852-226">javascript</span><span class="sxs-lookup"><span data-stu-id="6e852-226">javascript</span></span>|
|<span data-ttu-id="6e852-227">JSON</span><span class="sxs-lookup"><span data-stu-id="6e852-227">JSON</span></span>|<span data-ttu-id="6e852-228">json</span><span class="sxs-lookup"><span data-stu-id="6e852-228">json</span></span>|
|<span data-ttu-id="6e852-229">Markdown</span><span class="sxs-lookup"><span data-stu-id="6e852-229">Markdown</span></span>|<span data-ttu-id="6e852-230">md</span><span class="sxs-lookup"><span data-stu-id="6e852-230">md</span></span>|
|<span data-ttu-id="6e852-231">NodeJS</span><span class="sxs-lookup"><span data-stu-id="6e852-231">NodeJS</span></span>|<span data-ttu-id="6e852-232">nodejs</span><span class="sxs-lookup"><span data-stu-id="6e852-232">nodejs</span></span>|
|<span data-ttu-id="6e852-233">Objective-C</span><span class="sxs-lookup"><span data-stu-id="6e852-233">Objective-C</span></span>|<span data-ttu-id="6e852-234">objc</span><span class="sxs-lookup"><span data-stu-id="6e852-234">objc</span></span>|
|<span data-ttu-id="6e852-235">OData</span><span class="sxs-lookup"><span data-stu-id="6e852-235">OData</span></span>|<span data-ttu-id="6e852-236">odata</span><span class="sxs-lookup"><span data-stu-id="6e852-236">odata</span></span>|
|<span data-ttu-id="6e852-237">PHP</span><span class="sxs-lookup"><span data-stu-id="6e852-237">PHP</span></span>|<span data-ttu-id="6e852-238">php</span><span class="sxs-lookup"><span data-stu-id="6e852-238">php</span></span>|
|<span data-ttu-id="6e852-239">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="6e852-239">Power Apps Formula</span></span>|<span data-ttu-id="6e852-240">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="6e852-240">powerappsfl</span></span>|
|<span data-ttu-id="6e852-241">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e852-241">PowerShell</span></span>|<span data-ttu-id="6e852-242">powershell</span><span class="sxs-lookup"><span data-stu-id="6e852-242">powershell</span></span>|
|<span data-ttu-id="6e852-243">Python</span><span class="sxs-lookup"><span data-stu-id="6e852-243">Python</span></span>|<span data-ttu-id="6e852-244">python</span><span class="sxs-lookup"><span data-stu-id="6e852-244">python</span></span>|
|<span data-ttu-id="6e852-245">Q#</span><span class="sxs-lookup"><span data-stu-id="6e852-245">Q#</span></span>|<span data-ttu-id="6e852-246">qsharp</span><span class="sxs-lookup"><span data-stu-id="6e852-246">qsharp</span></span>|
|<span data-ttu-id="6e852-247">Ruby</span><span class="sxs-lookup"><span data-stu-id="6e852-247">Ruby</span></span>|<span data-ttu-id="6e852-248">ruby</span><span class="sxs-lookup"><span data-stu-id="6e852-248">ruby</span></span>|
|<span data-ttu-id="6e852-249">SQL</span><span class="sxs-lookup"><span data-stu-id="6e852-249">SQL</span></span>|<span data-ttu-id="6e852-250">sql</span><span class="sxs-lookup"><span data-stu-id="6e852-250">sql</span></span>|
|<span data-ttu-id="6e852-251">Swift</span><span class="sxs-lookup"><span data-stu-id="6e852-251">Swift</span></span>|<span data-ttu-id="6e852-252">swift</span><span class="sxs-lookup"><span data-stu-id="6e852-252">swift</span></span>|
|<span data-ttu-id="6e852-253">TypeScript</span><span class="sxs-lookup"><span data-stu-id="6e852-253">TypeScript</span></span>|<span data-ttu-id="6e852-254">typescript</span><span class="sxs-lookup"><span data-stu-id="6e852-254">typescript</span></span>|
|<span data-ttu-id="6e852-255">VB</span><span class="sxs-lookup"><span data-stu-id="6e852-255">VB</span></span>|<span data-ttu-id="6e852-256">vb</span><span class="sxs-lookup"><span data-stu-id="6e852-256">vb</span></span>|
|<span data-ttu-id="6e852-257">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="6e852-257">VSTS CLI</span></span>|<span data-ttu-id="6e852-258">vstscli</span><span class="sxs-lookup"><span data-stu-id="6e852-258">vstscli</span></span>|
|<span data-ttu-id="6e852-259">XAML</span><span class="sxs-lookup"><span data-stu-id="6e852-259">XAML</span></span>|<span data-ttu-id="6e852-260">xaml</span><span class="sxs-lookup"><span data-stu-id="6e852-260">xaml</span></span>|
|<span data-ttu-id="6e852-261">XML</span><span class="sxs-lookup"><span data-stu-id="6e852-261">XML</span></span>|<span data-ttu-id="6e852-262">xml</span><span class="sxs-lookup"><span data-stu-id="6e852-262">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="6e852-263">Exempel: C\#</span><span class="sxs-lookup"><span data-stu-id="6e852-263">Example: C\#</span></span>

<span data-ttu-id="6e852-264">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="6e852-264">__Markdown__</span></span>

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

<span data-ttu-id="6e852-265">__Rendera__</span><span class="sxs-lookup"><span data-stu-id="6e852-265">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="6e852-266">Exempel: SQL</span><span class="sxs-lookup"><span data-stu-id="6e852-266">Example: SQL</span></span>

<span data-ttu-id="6e852-267">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="6e852-267">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="6e852-268">__Rendera__</span><span class="sxs-lookup"><span data-stu-id="6e852-268">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="6e852-269">OPS-anpassade Markdown-förlängningar</span><span class="sxs-lookup"><span data-stu-id="6e852-269">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="6e852-270">Open Publishing Services (OPS) implementerar DocFX Flavored Markdown (DFM), som är mycket kompatibel med GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="6e852-270">Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM), which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="6e852-271">DFM lägger till vissa ytterligare funktioner via Markdown-tillägg.</span><span class="sxs-lookup"><span data-stu-id="6e852-271">DFM adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="6e852-272">Utvalda artiklar från den fullständiga OPS-redigeringsguiden ingår till exempel i den här handboken som referens.</span><span class="sxs-lookup"><span data-stu-id="6e852-272">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="6e852-273">(Se till exempel ”DFM och Markdown-tillägg” och ”Kodfragment” i innehållsförteckningen.)</span><span class="sxs-lookup"><span data-stu-id="6e852-273">(For example, see "DFM and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="6e852-274">Docs-artiklar använder GFM för de flesta formerna av artikelformatering, som stycken, länkar, listor och rubriker.</span><span class="sxs-lookup"><span data-stu-id="6e852-274">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="6e852-275">För en djupare formatering kan artiklar använda DFM-funktioner som:</span><span class="sxs-lookup"><span data-stu-id="6e852-275">For richer formatting, articles can use DFM features such as:</span></span>

- <span data-ttu-id="6e852-276">Anteckningsblock</span><span class="sxs-lookup"><span data-stu-id="6e852-276">Note blocks</span></span>
- <span data-ttu-id="6e852-277">Inkluderar</span><span class="sxs-lookup"><span data-stu-id="6e852-277">Includes</span></span>
- <span data-ttu-id="6e852-278">Väljare</span><span class="sxs-lookup"><span data-stu-id="6e852-278">Selectors</span></span>
- <span data-ttu-id="6e852-279">Inbäddade videoklipp</span><span class="sxs-lookup"><span data-stu-id="6e852-279">Embedded videos</span></span>
- <span data-ttu-id="6e852-280">Kodfragment/-exempel</span><span class="sxs-lookup"><span data-stu-id="6e852-280">Code snippets/samples</span></span>

<span data-ttu-id="6e852-281">För en fullständig lista, se ”DFM- och Markdown-tillägg” och ”Kodfragment” i innehållsförteckningen.</span><span class="sxs-lookup"><span data-stu-id="6e852-281">For the complete list, refer to "DFM and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="6e852-282">Anteckningsblock</span><span class="sxs-lookup"><span data-stu-id="6e852-282">Note blocks</span></span>

<span data-ttu-id="6e852-283">Du kan välja bland fyra typer av anteckningsblock för att markera specifikt innehåll:</span><span class="sxs-lookup"><span data-stu-id="6e852-283">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="6e852-284">OBS</span><span class="sxs-lookup"><span data-stu-id="6e852-284">NOTE</span></span>
- <span data-ttu-id="6e852-285">VARNING</span><span class="sxs-lookup"><span data-stu-id="6e852-285">WARNING</span></span>
- <span data-ttu-id="6e852-286">TIPS</span><span class="sxs-lookup"><span data-stu-id="6e852-286">TIP</span></span>
- <span data-ttu-id="6e852-287">VIKTIGT</span><span class="sxs-lookup"><span data-stu-id="6e852-287">IMPORTANT</span></span>

<span data-ttu-id="6e852-288">Som regel bör anteckningsblock användas sparsamt eftersom de kan vara störande.</span><span class="sxs-lookup"><span data-stu-id="6e852-288">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="6e852-289">Anteckningsblock stöder kodblock, bilder, listor och länkar, men bör vara så enkla som möjligt.</span><span class="sxs-lookup"><span data-stu-id="6e852-289">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="6e852-290">Inkluderar</span><span class="sxs-lookup"><span data-stu-id="6e852-290">Includes</span></span>

<span data-ttu-id="6e852-291">När du har en text- eller bildfil som kan återanvändas och som måste ingå i artikelfiler kan du använda en referens som "inkluderar" filen via funktionen inkludera fil i DFM.</span><span class="sxs-lookup"><span data-stu-id="6e852-291">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the DFM file include feature.</span></span> <span data-ttu-id="6e852-292">Funktionen ger OPS en instruktion att inkludera den angivna filen i din artikelfil när den byggs, vilket gör den till en del av den publicerade artikeln.</span><span class="sxs-lookup"><span data-stu-id="6e852-292">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="6e852-293">Det finns tre typer av inkluderingar som hjälper dig att återanvända innehåll:</span><span class="sxs-lookup"><span data-stu-id="6e852-293">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="6e852-294">Intern – Återanvänd en vanlig textsträng i en annan mening.</span><span class="sxs-lookup"><span data-stu-id="6e852-294">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="6e852-295">Block – Återanvänd en hel Markdown-fil som ett block som bäddas in i en del av artikeln.</span><span class="sxs-lookup"><span data-stu-id="6e852-295">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="6e852-296">Bild – Detta är standardsättet att inkludera bilder i Docs.</span><span class="sxs-lookup"><span data-stu-id="6e852-296">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="6e852-297">Interna inkluderingar och blockinkluderingar är bara enkla Markdown-filer (.md).</span><span class="sxs-lookup"><span data-stu-id="6e852-297">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="6e852-298">De kan innehålla alla sorters giltiga Markdowns.</span><span class="sxs-lookup"><span data-stu-id="6e852-298">It can contain any valid Markdown.</span></span> <span data-ttu-id="6e852-299">Alla inkluderingsfiler i Markdown bör placeras i en [gemensam`/includes` underkatalog](git-github-fundamentals.md#includes-subdirectory) i lagringsplatsens rot.</span><span class="sxs-lookup"><span data-stu-id="6e852-299">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="6e852-300">När artikeln publiceras integreras den inkluderade filen sömlöst i den publicerade artikeln.</span><span class="sxs-lookup"><span data-stu-id="6e852-300">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="6e852-301">Här följer krav och överväganden för inkluderingar:</span><span class="sxs-lookup"><span data-stu-id="6e852-301">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="6e852-302">Använd inkludera när du vill att samma text ska visas i flera artiklar.</span><span class="sxs-lookup"><span data-stu-id="6e852-302">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="6e852-303">Använd blockinkluderingar för stora mängder innehåll – ett stycke eller två, en delad procedur eller ett delat avsnitt.</span><span class="sxs-lookup"><span data-stu-id="6e852-303">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="6e852-304">Använd dem inte för mindre än en mening.</span><span class="sxs-lookup"><span data-stu-id="6e852-304">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="6e852-305">Inkluderat innehåll återges inte i den renderade vyn för din artikel i GitHub eftersom de använder DFM-tillägg.</span><span class="sxs-lookup"><span data-stu-id="6e852-305">Includes won't be rendered in the GitHub rendered view of your article, because they rely on DFM extensions.</span></span> <span data-ttu-id="6e852-306">De återges först efter publiceringen.</span><span class="sxs-lookup"><span data-stu-id="6e852-306">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="6e852-307">Kontrollera att all text i en inkludering är skriven i fullständiga meningar eller satser som inte är beroende av föregående eller efterföljande text i artikeln som använder den inkluderade texten.</span><span class="sxs-lookup"><span data-stu-id="6e852-307">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="6e852-308">Om du hoppar över detta steg kan en sträng som inte kan översättas skapas, vilket stör den lokaliserade upplevelsen.</span><span class="sxs-lookup"><span data-stu-id="6e852-308">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="6e852-309">Bädda inte in inkluderingar med andra inkluderingar.</span><span class="sxs-lookup"><span data-stu-id="6e852-309">Don't embed includes within other includes.</span></span> <span data-ttu-id="6e852-310">De stöds inte.</span><span class="sxs-lookup"><span data-stu-id="6e852-310">They are not supported.</span></span>
- <span data-ttu-id="6e852-311">Placera mediefiler i en mediemapp som är specifik för inkluderingsunderkatalogen – till exempel, `<repo>`/inkluderingar/mediamapp.</span><span class="sxs-lookup"><span data-stu-id="6e852-311">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="6e852-312">Mediekatalogen bör inte innehålla några bilder i sin rot.</span><span class="sxs-lookup"><span data-stu-id="6e852-312">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="6e852-313">Om inkluderingen inte har bilder behövs inte en motsvarande mediekatalog.</span><span class="sxs-lookup"><span data-stu-id="6e852-313">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="6e852-314">Precis som med vanliga artiklar bör du inte dela media mellan inkluderingsfiler.</span><span class="sxs-lookup"><span data-stu-id="6e852-314">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="6e852-315">Använd en särskild fil med ett unikt namn för varje inkludering och artikel.</span><span class="sxs-lookup"><span data-stu-id="6e852-315">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="6e852-316">Lagra mediefilen i mediemappen som associeras med inkluderingen.</span><span class="sxs-lookup"><span data-stu-id="6e852-316">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="6e852-317">Använd inte en inkludering som det enda innehållet i en artikel.</span><span class="sxs-lookup"><span data-stu-id="6e852-317">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="6e852-318">Inkluderingar är avsedda att komplettera övrigt innehåll i en artikel.</span><span class="sxs-lookup"><span data-stu-id="6e852-318">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="6e852-319">Väljare</span><span class="sxs-lookup"><span data-stu-id="6e852-319">Selectors</span></span>

<span data-ttu-id="6e852-320">Använd väljare i tekniska artiklar när du skriver olika versioner av samma artikel för att visa implementeringsskillnader för olika tekniker eller plattformar.</span><span class="sxs-lookup"><span data-stu-id="6e852-320">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="6e852-321">Detta gäller framför allt för innehåll vår plattform för mobilt innehåll för utvecklare.</span><span class="sxs-lookup"><span data-stu-id="6e852-321">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="6e852-322">Det finns för närvarande två typer av väljare i DFM: en enkel väljare och en multiväljare.</span><span class="sxs-lookup"><span data-stu-id="6e852-322">There are currently two different types of selectors in DFM, a single selector and a multi-selector.</span></span>

<span data-ttu-id="6e852-323">Eftersom samma Markdown för väljare används i alla markerade artiklar rekommenderar vi att du placerar väljaren för en artikel i en inkludering.</span><span class="sxs-lookup"><span data-stu-id="6e852-323">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="6e852-324">Du kan sedan hänvisa till den inkluderingen i alla artiklar som använder samma väljare.</span><span class="sxs-lookup"><span data-stu-id="6e852-324">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="6e852-325">Kodfragment</span><span class="sxs-lookup"><span data-stu-id="6e852-325">Code snippets</span></span>

<span data-ttu-id="6e852-326">DFM har stöd för avancerad inkludering av kod i artiklar, tack vare kodfragmentstillägget.</span><span class="sxs-lookup"><span data-stu-id="6e852-326">DFM supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="6e852-327">Tillägget möjliggör avancerad rendering som bygger på GFM-funktioner som programmeringsspråkval och syntaxfärgning, samt användbara funktioner som:</span><span class="sxs-lookup"><span data-stu-id="6e852-327">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="6e852-328">Inkludering av centraliserade kodexempel/-fragment från externa lagringsplatser.</span><span class="sxs-lookup"><span data-stu-id="6e852-328">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="6e852-329">Användargränssnitt i flikar för att visa olika versioner av kodexempel i olika språk.</span><span class="sxs-lookup"><span data-stu-id="6e852-329">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="6e852-330">Information och felsökning</span><span class="sxs-lookup"><span data-stu-id="6e852-330">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="6e852-331">Alternativ text</span><span class="sxs-lookup"><span data-stu-id="6e852-331">Alt text</span></span>

<span data-ttu-id="6e852-332">Alternativ text som innehåller understreck återges inte korrekt.</span><span class="sxs-lookup"><span data-stu-id="6e852-332">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="6e852-333">Till exempel, i stället för att använda detta:</span><span class="sxs-lookup"><span data-stu-id="6e852-333">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="6e852-334">Använd escape-tecken för understrecken, så här:</span><span class="sxs-lookup"><span data-stu-id="6e852-334">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="6e852-335">Apostrofer och citattecken</span><span class="sxs-lookup"><span data-stu-id="6e852-335">Apostrophes and quotation marks</span></span>

<span data-ttu-id="6e852-336">Om du kopierar från Word till en Markdown-redigerare kan texten innehålla ”smarta”(sneda) apostrofer eller citattecken.</span><span class="sxs-lookup"><span data-stu-id="6e852-336">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="6e852-337">Dessa måste vara kodade eller ändras till raka apostrofer eller citattecken.</span><span class="sxs-lookup"><span data-stu-id="6e852-337">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="6e852-338">Annars kan det se ut så här när filen publiceras: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="6e852-338">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="6e852-339">Så här skriver du ”smarta” skiljetecken:</span><span class="sxs-lookup"><span data-stu-id="6e852-339">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="6e852-340">Vänster citattecken: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="6e852-340">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="6e852-341">Höger citattecken: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="6e852-341">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="6e852-342">Höger, enkelt citattecken eller apostrof: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="6e852-342">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="6e852-343">Vänster, enkelt citattecken: `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="6e852-343">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="6e852-344">Vinkelparentes</span><span class="sxs-lookup"><span data-stu-id="6e852-344">Angle brackets</span></span>

<span data-ttu-id="6e852-345">Om du använder vinkelparenteser i texten (inte koden) – till exempel för att markera en platshållare – måste du skriva hakparenteserna i kod.</span><span class="sxs-lookup"><span data-stu-id="6e852-345">If you use angle brackets in text (not code) in your file--for example, to denote a placeholder--you need to manually encode the angle brackets.</span></span> <span data-ttu-id="6e852-346">Annars tror Markdown att det är en HTML-tagg.</span><span class="sxs-lookup"><span data-stu-id="6e852-346">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="6e852-347">Till exempel, koda `<script name>` som `&lt;script name&gt;`</span><span class="sxs-lookup"><span data-stu-id="6e852-347">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="6e852-348">Se även</span><span class="sxs-lookup"><span data-stu-id="6e852-348">See also</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="6e852-349">Markdown-resurser</span><span class="sxs-lookup"><span data-stu-id="6e852-349">Markdown resources</span></span>

- [<span data-ttu-id="6e852-350">Introduktion till Markdown</span><span class="sxs-lookup"><span data-stu-id="6e852-350">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="6e852-351">Docs Markdown lathund</span><span class="sxs-lookup"><span data-stu-id="6e852-351">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="6e852-352">Grunder för Markdown i GitHub</span><span class="sxs-lookup"><span data-stu-id="6e852-352">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
