---
title: 'Snabbstart: Ställ in och hämta en hemlighet från Azure Key Vault | Microsoft Docs'
description: 'Snabbstart: Ställ in och hämta en hemlighet från Azure Key Vault'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 27ebd3e348fc231d8b82e6c17f282bd9ca4afb9f
ms.sourcegitcommit: 5e508a7ad2991632a38f302e4769b36e3bf37eb2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/30/2018
ms.locfileid: "43308834"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a>Snabbstart: Ställ in och hämta en hemlighet från Azure Key Vault

Den här snabbstarten beskriver hur du lagrar en hemlighet i Key Vault och hur du hämtar den med hjälp av en webbapp. För att visa det hemliga värdet skulle du behöva köra detta i Azure. I snabbstarten används Node.js och hanterade tjänstidentiteter (MSI)

> [!div class="checklist"]
> * Skapa ett nyckelvalv.
> * Lagra en hemlighet i Key Vault.
> * Hämta en hemlighet från Key Vault.
> * Skapa ett Azure-webbapp.
> * [Aktivera hanterade tjänstidentiteter](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).
> * Bevilja de behörigheter som krävs för att webbappen ska kunna läsa data från Key Vault.

Försäkra dig om att du känner till [grundbegreppen](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts) innan du fortsätter.

> [!NOTE]
> För att förstå varför självstudien nedan är bästa praxis är det viktigt att du förstår vissa begrepp. Key Vault är en central lagringsplats för programmeringsbaserad lagring av hemligheter. Detta kräver att program och användare först autentiseras mot Key Vault, dvs. presenterar en hemlighet. Den här första hemligheten måste dessutom roteras med jämna mellanrum för att uppfylla de rekommenderade säkerhetsmetoderna. Med [hanterad tjänstidentitet (MSI)](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) tilldelas program som körs i Azure en identitet som hanteras automatiskt av Azure. Detta löser **problemet med den första hemligheten** där användare och program kan följa regelverket utan att behöva bekymra sig om roteringen av den första hemligheten

## <a name="prerequisites"></a>Förhandskrav

::: zone pivot="nodejs"
* [Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"
* [Visual Studio 2017 version 15.7.3 eller senare](https://www.microsoft.com/net/download/windows) med följande arbetsbelastningar:
  * ASP.NET och webbutveckling
  * .NET Core plattformsoberoende utveckling
* [.NET Core 2.1 SDK eller senare](https://www.microsoft.com/net/download/windows) :::zone-end
* Git ([ladda ned](https://git-scm.com/downloads)).
* En Azure-prenumeration. Om du inte har en Azure-prenumeration kan du skapa ett [kostnadsfritt konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) innan du börjar.
* [Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 eller senare. Detta är tillgängligt för Windows, Mac och Linux.

## <a name="login-to-azure"></a>Logga in på Azure

Du kan logga in på Azure via CLI genom att skriva:

```azurecli
az login
```

## <a name="create-resource-group"></a>Skapa resursgrupp

Skapa en resursgrupp med kommandot [az group create](/cli/azure/group#az-group-create). En resursgrupp i Azure är en logisk behållare där Azure-resurser distribueras och hanteras.

Välj ett resursgruppnamn och fyll i platshållaren.
I följande exempel skapas en resursgrupp med namnet *<YourResourceGroupName>* på platsen *eastus*.

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

Resursgruppen som du nyss skapade används i hela den här självstudien.

## <a name="create-an-azure-key-vault"></a>Skapa ett Azure Key Vault

Nu ska du skapa ett nyckelvalv i resursgruppen som du skapade i föregående steg. ”ContosoKeyVault” används som namn på nyckelvalvet i hela den här artikeln, men det är viktigt att poängtera att du måste använda ett unikt namn. Ange följande information:

* Valvnamn – **välj ett Key Vault-namn här**.
* Resursgruppsnamn – **välj ett resursgruppsnamn här**.
* Plats – **USA, östra**.

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

Nu är ditt Azure-konto det enda kontot med behörighet att utföra åtgärder i det nya valvet.

## <a name="add-a-secret-to-key-vault"></a>Lägga till en hemlighet i Key Vault

Vi lägger till en hemlighet för att illustrera hur detta fungerar. Du kan lagra en SQL-anslutningssträng eller annan information som du behöver skydda men göra tillgänglig för ditt program. I den här självstudiekursen kallas lösenordet **AppSecret** och lagrar värdet för **MySecret**.

Skriv kommandona nedan för att skapa en hemlighet i Key Vault med namnet **AppSecret** som ska lagra värdet **MySecret**:

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

Så här visar du värdet som finns i hemligheten som oformaterad text:

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

Det här kommandot visar den hemliga informationen, inklusive URI:n. När du har slutfört de här stegen bör du ha en URI till en hemlighet i Azure Key Vault. Anteckna den här informationen. Du behöver den senare.

## <a name="clone-the-repo"></a>Klona lagringsplatsen

Klona lagringsplatsen för att skapa en lokal kopia så att du kan redigera källan genom att köra följande kommando:

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a>Installera beroenden

Här installera vi beroendena. Kör följande kommandon: cd key-vault-node-quickstart npm install

I det här projektet används 2 Node-moduler:

* [ms-rest-azure](https://www.npmjs.com/package/ms-rest-azure) 
* [azure-keyvault](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a>Publicera webbappen till Azure

Nedan beskrivs de få steg som krävs

* Det första steget är att skapa en [Azure App Service](https://azure.microsoft.com/services/app-service/)-plan. Du kan lagra flera webbappar i den här planen.

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* Därefter skapar vi en webbapp. I följande exempel ersätter du <app_name> med ett globalt, unikt appnamn (giltiga tecken är a-z, 0-9 och -). Körningen är inställd på NODE|6.9. Kör az webapp list-runtimes om du vill visa alla körningar

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    När webbappen har skapats visar Azure CLI utdata liknande den i följande exempel:

    ```json
    {
      "availabilityState": "Normal",
      "clientAffinityEnabled": true,
      "clientCertEnabled": false,
      "cloningInfo": null,
      "containerSize": 0,
      "dailyMemoryTimeQuota": 0,
      "defaultHostName": "<app_name>.azurewebsites.net",
      "enabled": true,
      "deploymentLocalGitUrl": "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git"
      < JSON data removed for brevity. >
    }
    ```
    Gå till den nya webbappen, så bör du se en fungerande webbapp. Ersätt <app_name> med ett unikt appnamn.

    ```text
    http://<app name>.azurewebsites.net
    ```
    Kommandot ovan skapar även en Git-aktiverad app som gör att du kan distribuera till Azure från din lokala git-lagringsplats. 
    Den lokala git-lagringsplatsen konfigureras med URL:en ”https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git”

* Skapa en distributionsanvändare. När det föregående kommandot har slutförts kan du lägga till en Azure-fjärranslutning till din lokala Git-lagringsplats. Ersätt <url> med URL:en för den fjärranslutna Git-lagringsplats som du fick från Aktivera Git för din app.

    ```bash
    git remote add azure <url>
    ```
    
::: zone-end

::: zone pivot="dotnet"
## <a name="open-and-edit-the-solution"></a>Öppna och redigera lösningen

Redigera filen program.cs för att köra exemplet med namnet på ditt specifika nyckelvalvsnamn:

1. Bläddra till mappen key-vault-dotnet-core-quickstart.
2. Öppna filen key-vault-dotnet-core-quickstart.sln i Visual Studio 2017.
3. Öppna filen Program.cs och uppdatera platshållaren *YourKeyVaultName* med namnet på det nyckelvalv som du skapade tidigare.

Den här lösningen använder NuGet-biblioteken [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) och [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).

## <a name="run-the-app"></a>Kör appen

På huvudmenyn för Visual Studio 2017 väljer du **Felsökning** > **Starta** utan felsökning. När webbläsaren visas går du till sidan **Om**. Värdet för **AppSecret** visas.

## <a name="publish-the-web-application-to-azure"></a>Publicera webbappen till Azure

Publicera den här appen till Azure för att se den live som en webbapp och se att du kan hämta det hemliga värdet:

1. I Visual Studio väljer du projektet **key-vault-dotnet-core-quickstart**.
2. Välj **Publicera** > **Start**.
3. Skapa en ny **App Service** och välj sedan **Publicera**.
4. Ändra namnet på appen till **keyvaultdotnetcorequickstart**.
5. Välj **Skapa**.

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]
::: zone-end

## <a name="enable-managed-service-identities"></a>Aktivera hanterade tjänstidentiteter

Azure Key Vault är ett sätt att lagra autentiseringsuppgifter samt andra nycklar och hemligheter på ett säkert sätt, men din kod måste autentiseras till Azure Key Vault för att kunna hämta dem. Hanterad tjänstidentitet gör det här enklare genom att ge Azure-tjänsterna en automatiskt hanterad identitet i Azure Active Directory (Azure AD). Du kan använda den här identiteten för att autentisera till alla tjänster som stöder Azure AD-autentisering, inklusive Key Vault, utan att behöva ha några autentiseringsuppgifter i koden.

1. Gå tillbaka till Azure CLI.
2. Kör kommandot assign-identity för att skapa identiteten för det här programmet:

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
>Kommandot i denna proceduren fungerar på samma sätt som när du går till portalen och väljer **På** för **Hanterad tjänstidentitet** i egenskaperna för webbprogrammet.

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a>Tilldela behörigheter till ditt program att läsa hemligheter från Key Vault

Anteckna utdata när du publicerar programmet till Azure. Det ska vara i formatet:

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

Kör sedan det här kommandot med namnet på ditt nyckelvalv och värdet för **PrincipalId**:

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a>Distribuera Node-appen till Azure och hämta det hemliga värdet

Nu är allt konfigurerat. Distribuera appen till Azure genom att köra följande kommando

```bash
git push azure master
```

När du har gjort det och går till https://<app_name>.azurewebsites.net kan du se det hemliga värdet.
Kontrollera att du ersatte namnet <YourKeyVaultName> med namnet på ditt valv

::: zone-end

::: zone pivot="dotnet" Nu när du kör programmet bör ditt hemliga värde hämtas.
::: zone-end

## <a name="next-steps"></a>Nästa steg

::: zone pivot="nodejs"
* [Startsida för Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Dokumentation om Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [Azure SDK för Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* [Azure REST API-referens](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end

::: zone pivot="dotnet"
* [Startsida för Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Dokumentation om Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [Azure SDK för .NET](https://github.com/Azure/azure-sdk-for-net)
* [Azure REST API-referens](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end
