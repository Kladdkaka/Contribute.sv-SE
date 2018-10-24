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
# <a name="docs-pr-validation-service"></a>Docs PR-valideringstjänst

Docs PR-valideringstjänsten är en GitHub-app som kör valideringsregler på filer i en PR.

När valideringstjänsten är aktiverad på en lagringsplats kan du se följande beteende:

1. Du skickar en PR.
1. I GitHub-kommentaren som anger status för din PR kan du se att status "checks" (kontroller) har aktiverats på lagringsplatsen. Observera att två kontroller är aktiverade i det här exemplet: "Commit Validation" och "OpenPublishing.Build":

   ![vissa kontroller misslyckades](media/validation-failed.png)

   Versionen kan godkännas även om valideringen misslyckas.

1. Klicka på **Details** (Detaljerad information) om du vill ha mer information.
1. På sidan Details (Detaljerad information) visas alla valideringskontroller som har misslyckats och information om hur du åtgärdar problemen:

   ![valideringsmeddelande](media/validation-details.png)

En lista med de valideringar som för närvarande finns i tjänsten visas i innehållsförteckningen till vänster.