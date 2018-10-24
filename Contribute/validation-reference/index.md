---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084627"
---
# <a name="docs-pr-validation-service"></a><span data-ttu-id="70bb4-101">Docs PR-valideringstjänst</span><span class="sxs-lookup"><span data-stu-id="70bb4-101">Docs PR validation service</span></span>

<span data-ttu-id="70bb4-102">Docs PR-valideringstjänsten är en GitHub-app som kör valideringsregler på filer i en PR.</span><span class="sxs-lookup"><span data-stu-id="70bb4-102">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span>

<span data-ttu-id="70bb4-103">När valideringstjänsten är aktiverad på en lagringsplats kan du se följande beteende:</span><span class="sxs-lookup"><span data-stu-id="70bb4-103">When the validation service is enabled on a repo, you'll see the following behavior:</span></span>

1. <span data-ttu-id="70bb4-104">Du skickar en PR.</span><span class="sxs-lookup"><span data-stu-id="70bb4-104">You submit a PR.</span></span>
1. <span data-ttu-id="70bb4-105">I GitHub-kommentaren som anger status för din PR kan du se att status "checks" (kontroller) har aktiverats på lagringsplatsen.</span><span class="sxs-lookup"><span data-stu-id="70bb4-105">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="70bb4-106">Observera att två kontroller är aktiverade i det här exemplet: "Commit Validation" och "OpenPublishing.Build":</span><span class="sxs-lookup"><span data-stu-id="70bb4-106">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![vissa kontroller misslyckades](media/validation-failed.png)

   <span data-ttu-id="70bb4-108">Versionen kan godkännas även om valideringen misslyckas.</span><span class="sxs-lookup"><span data-stu-id="70bb4-108">Build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="70bb4-109">Klicka på **Details** (Detaljerad information) om du vill ha mer information.</span><span class="sxs-lookup"><span data-stu-id="70bb4-109">Click **Details** for more information.</span></span>
1. <span data-ttu-id="70bb4-110">På sidan Details (Detaljerad information) visas alla valideringskontroller som har misslyckats och information om hur du åtgärdar problemen:</span><span class="sxs-lookup"><span data-stu-id="70bb4-110">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues:</span></span>

   ![valideringsmeddelande](media/validation-details.png)

<span data-ttu-id="70bb4-112">En lista med de valideringar som för närvarande finns i tjänsten visas i innehållsförteckningen till vänster.</span><span class="sxs-lookup"><span data-stu-id="70bb4-112">See the left-hand TOC of this article for the list of validations currently in the service.</span></span>