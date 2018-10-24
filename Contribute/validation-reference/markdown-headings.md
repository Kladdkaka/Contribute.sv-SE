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
# <a name="markdown-headings"></a>Markdown-rubriker

Följande valideringskrav gäller huvuden i OPS Markdown-filer.

## <a name="h1"></a>H1

`H1` refererar till den första rubriknivån i en Markdown-fil. Vid publicering på docs.microsoft.com visas H1 längst upp på sidan med stora tecken.

H1 skapas genom att en rad inleds med ett enkelt nummertecken (`#`) följt av ett blanksteg och sedan rubriktexten. H1 för den här artikeln är till exempel:

```md
# Markdown headings
```

Följande regler gäller för H1-rubriker:

- H1 måste finnas i filen.
- H1 får bara förekomma en gång.
- H1 måste ha ett innehåll.

  ```markdown
  # 
  This is not allowed.
  ```
- Det måste finnas ett blanksteg mellan `#` och H1-innehållet. H1 utan blanksteg återges inte som en rubrik på den publicerade sidan.

  ```markdown
  #This looks bad on the site.
  ```
- H1 måste vara det första innehållet i filet efter YML-metadatarubriken. Det får inte finnas något innehåll, till exempel text eller bilder, mellan slutet av YML-rubriken och H1.

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- HTML-element för rubriker på första nivån, `<h1>`, får inte användas. Använd Markdown-syntaxen (`# `).
- H1 får inte vara längre än 100 tecken. Det här är en skrivregel.

## <a name="h2---h6"></a>H2–H6

H2 (`## `) till H6 (`###### `) är tillåtna i OPS. Använd Markdown-rubriker, inte HTML (`<h2>` - `<h6>`), när du skapar rubriker.
