---
title: Markdown-rubriker
description: Beskriver kraven för Markdown-rubriker.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 05/03/2017
ms.openlocfilehash: 18beb815fdf7caad3e8e675e8d79853d8a5688f2
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084565"
---
# <a name="markdown-headings"></a><span data-ttu-id="7c73c-103">Markdown-rubriker</span><span class="sxs-lookup"><span data-stu-id="7c73c-103">Markdown headings</span></span>

<span data-ttu-id="7c73c-104">Följande valideringskrav gäller huvuden i OPS Markdown-filer.</span><span class="sxs-lookup"><span data-stu-id="7c73c-104">The following validation requirements apply to headings in OPS Markdown files.</span></span>

## <a name="h1"></a><span data-ttu-id="7c73c-105">H1</span><span class="sxs-lookup"><span data-stu-id="7c73c-105">H1</span></span>

<span data-ttu-id="7c73c-106">`H1` refererar till den första rubriknivån i en Markdown-fil.</span><span class="sxs-lookup"><span data-stu-id="7c73c-106">`H1` refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="7c73c-107">Vid publicering på docs.microsoft.com visas H1 längst upp på sidan med stora tecken.</span><span class="sxs-lookup"><span data-stu-id="7c73c-107">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span>

<span data-ttu-id="7c73c-108">H1 skapas genom att en rad inleds med ett enkelt nummertecken (`#`) följt av ett blanksteg och sedan rubriktexten.</span><span class="sxs-lookup"><span data-stu-id="7c73c-108">An H1 is created by beginning a line with a single hash (`#`) followed by a space, then the heading text.</span></span> <span data-ttu-id="7c73c-109">H1 för den här artikeln är till exempel:</span><span class="sxs-lookup"><span data-stu-id="7c73c-109">For example, the H1 of this article is:</span></span>

```md
# Markdown headings
```

<span data-ttu-id="7c73c-110">Följande regler gäller för H1-rubriker:</span><span class="sxs-lookup"><span data-stu-id="7c73c-110">The following rules apply to H1 headings:</span></span>

- <span data-ttu-id="7c73c-111">H1 måste finnas i filen.</span><span class="sxs-lookup"><span data-stu-id="7c73c-111">An H1 must be present in the file.</span></span>
- <span data-ttu-id="7c73c-112">H1 får bara förekomma en gång.</span><span class="sxs-lookup"><span data-stu-id="7c73c-112">There can only be one H1.</span></span>
- <span data-ttu-id="7c73c-113">H1 måste ha ett innehåll.</span><span class="sxs-lookup"><span data-stu-id="7c73c-113">The H1 must have content.</span></span>

  ```markdown
  # 
  This is not allowed.
  ```
- <span data-ttu-id="7c73c-114">Det måste finnas ett blanksteg mellan `#` och H1-innehållet.</span><span class="sxs-lookup"><span data-stu-id="7c73c-114">There must be a space between the `#` and the H1 content.</span></span> <span data-ttu-id="7c73c-115">H1 utan blanksteg återges inte som en rubrik på den publicerade sidan.</span><span class="sxs-lookup"><span data-stu-id="7c73c-115">An H1 with no space doesn't render as a heading on the published page.</span></span>

  ```markdown
  #This looks bad on the site.
  ```
- <span data-ttu-id="7c73c-116">H1 måste vara det första innehållet i filet efter YML-metadatarubriken.</span><span class="sxs-lookup"><span data-stu-id="7c73c-116">The H1 must be the first content in the file after the YML metadata header.</span></span> <span data-ttu-id="7c73c-117">Det får inte finnas något innehåll, till exempel text eller bilder, mellan slutet av YML-rubriken och H1.</span><span class="sxs-lookup"><span data-stu-id="7c73c-117">No content, such as text or images, is allowed between the end of the YML header and the H1.</span></span>

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- <span data-ttu-id="7c73c-118">HTML-element för rubriker på första nivån, `<h1>`, får inte användas.</span><span class="sxs-lookup"><span data-stu-id="7c73c-118">The HTML element for first-level headings, `<h1>`, should not be used.</span></span> <span data-ttu-id="7c73c-119">Använd Markdown-syntaxen (`# `).</span><span class="sxs-lookup"><span data-stu-id="7c73c-119">Use the Markdown syntax (`# `).</span></span>
- <span data-ttu-id="7c73c-120">H1 får inte vara längre än 100 tecken.</span><span class="sxs-lookup"><span data-stu-id="7c73c-120">The H1 should be no more than 100 characters long.</span></span> <span data-ttu-id="7c73c-121">Det här är en skrivregel.</span><span class="sxs-lookup"><span data-stu-id="7c73c-121">This is a style guideline.</span></span>

## <a name="h2---h6"></a><span data-ttu-id="7c73c-122">H2–H6</span><span class="sxs-lookup"><span data-stu-id="7c73c-122">H2 - H6</span></span>

<span data-ttu-id="7c73c-123">H2 (`## `) till H6 (`###### `) är tillåtna i OPS.</span><span class="sxs-lookup"><span data-stu-id="7c73c-123">H2 (`## `) through H6 (`###### `) are allowed in OPS.</span></span> <span data-ttu-id="7c73c-124">Använd Markdown-rubriker, inte HTML (`<h2>` - `<h6>`), när du skapar rubriker.</span><span class="sxs-lookup"><span data-stu-id="7c73c-124">Use the Markdown headers, not the HTML (`<h2>` - `<h6>`), to create headings.</span></span>
