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
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a><span data-ttu-id="52562-103">Snabbstart: Ställ in och hämta en hemlighet från Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-103">Quickstart: Set and retrieve a secret from Azure Key Vault</span></span>

<span data-ttu-id="52562-104">Den här snabbstarten beskriver hur du lagrar en hemlighet i Key Vault och hur du hämtar den med hjälp av en webbapp.</span><span class="sxs-lookup"><span data-stu-id="52562-104">This quickstart shows you how to store a secret in Key Vault and how to retrieve it using a Web app.</span></span> <span data-ttu-id="52562-105">För att visa det hemliga värdet skulle du behöva köra detta i Azure.</span><span class="sxs-lookup"><span data-stu-id="52562-105">To see the secret value you would have to run this on Azure.</span></span> <span data-ttu-id="52562-106">I snabbstarten används Node.js och hanterade tjänstidentiteter (MSI)</span><span class="sxs-lookup"><span data-stu-id="52562-106">The quickstart uses Node.js and Managed service identities (MSIs)</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="52562-107">Skapa ett nyckelvalv.</span><span class="sxs-lookup"><span data-stu-id="52562-107">Create a Key Vault.</span></span>
> * <span data-ttu-id="52562-108">Lagra en hemlighet i Key Vault.</span><span class="sxs-lookup"><span data-stu-id="52562-108">Store a secret in Key Vault.</span></span>
> * <span data-ttu-id="52562-109">Hämta en hemlighet från Key Vault.</span><span class="sxs-lookup"><span data-stu-id="52562-109">Retrieve a secret from Key Vault.</span></span>
> * <span data-ttu-id="52562-110">Skapa ett Azure-webbapp.</span><span class="sxs-lookup"><span data-stu-id="52562-110">Create an Azure Web Application.</span></span>
> * <span data-ttu-id="52562-111">[Aktivera hanterade tjänstidentiteter](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span><span class="sxs-lookup"><span data-stu-id="52562-111">[Enable managed service identities](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span></span>
> * <span data-ttu-id="52562-112">Bevilja de behörigheter som krävs för att webbappen ska kunna läsa data från Key Vault.</span><span class="sxs-lookup"><span data-stu-id="52562-112">Grant the required permissions for the web application to read data from Key vault.</span></span>

<span data-ttu-id="52562-113">Försäkra dig om att du känner till [grundbegreppen](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts) innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="52562-113">Before you proceed make sure that you are familiar with the [basic concepts](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span></span>

> [!NOTE]
> <span data-ttu-id="52562-114">För att förstå varför självstudien nedan är bästa praxis är det viktigt att du förstår vissa begrepp.</span><span class="sxs-lookup"><span data-stu-id="52562-114">To understand why the below tutorial is the best practice we need to understand a few concepts.</span></span> <span data-ttu-id="52562-115">Key Vault är en central lagringsplats för programmeringsbaserad lagring av hemligheter.</span><span class="sxs-lookup"><span data-stu-id="52562-115">Key Vault is a central repository to store secrets programmatically.</span></span> <span data-ttu-id="52562-116">Detta kräver att program och användare först autentiseras mot Key Vault, dvs. presenterar en hemlighet.</span><span class="sxs-lookup"><span data-stu-id="52562-116">But to do so applications / users need to first authenticate to Key Vault i.e. present a secret.</span></span> <span data-ttu-id="52562-117">Den här första hemligheten måste dessutom roteras med jämna mellanrum för att uppfylla de rekommenderade säkerhetsmetoderna.</span><span class="sxs-lookup"><span data-stu-id="52562-117">To follow security best practices this first secret needs to be rotated periodically as well.</span></span> <span data-ttu-id="52562-118">Med [hanterad tjänstidentitet (MSI)](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) tilldelas program som körs i Azure en identitet som hanteras automatiskt av Azure.</span><span class="sxs-lookup"><span data-stu-id="52562-118">But with [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) applications that run in Azure are given an identity which is automatically managed by Azure.</span></span> <span data-ttu-id="52562-119">Detta löser **problemet med den första hemligheten** där användare och program kan följa regelverket utan att behöva bekymra sig om roteringen av den första hemligheten</span><span class="sxs-lookup"><span data-stu-id="52562-119">This helps solve the **Secret Introduction Problem** where users / applications can follow best practices and not have to worry about rotating the first secret</span></span>

## <a name="prerequisites"></a><span data-ttu-id="52562-120">Förhandskrav</span><span class="sxs-lookup"><span data-stu-id="52562-120">Prerequisites</span></span>

<span data-ttu-id="52562-121">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="52562-121">::: zone pivot="nodejs"</span></span>
* <span data-ttu-id="52562-122">[Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="52562-122">[Node JS](https://nodejs.org/en/) ::: zone-end ::: zone pivot="dotnet"</span></span>
* <span data-ttu-id="52562-123">[Visual Studio 2017 version 15.7.3 eller senare](https://www.microsoft.com/net/download/windows) med följande arbetsbelastningar:</span><span class="sxs-lookup"><span data-stu-id="52562-123">[Visual Studio 2017 version 15.7.3 or later](https://www.microsoft.com/net/download/windows) with the following workloads:</span></span>
  * <span data-ttu-id="52562-124">ASP.NET och webbutveckling</span><span class="sxs-lookup"><span data-stu-id="52562-124">ASP.NET and web development</span></span>
  * <span data-ttu-id="52562-125">.NET Core plattformsoberoende utveckling</span><span class="sxs-lookup"><span data-stu-id="52562-125">.NET Core cross-platform development</span></span>
* <span data-ttu-id="52562-126">[.NET Core 2.1 SDK eller senare](https://www.microsoft.com/net/download/windows) :::zone-end</span><span class="sxs-lookup"><span data-stu-id="52562-126">[.NET Core 2.1 SDK or later](https://www.microsoft.com/net/download/windows) ::: zone-end</span></span>
* <span data-ttu-id="52562-127">Git ([ladda ned](https://git-scm.com/downloads)).</span><span class="sxs-lookup"><span data-stu-id="52562-127">Git ([download](https://git-scm.com/downloads)).</span></span>
* <span data-ttu-id="52562-128">En Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="52562-128">An Azure subscription.</span></span> <span data-ttu-id="52562-129">Om du inte har en Azure-prenumeration kan du skapa ett [kostnadsfritt konto](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) innan du börjar.</span><span class="sxs-lookup"><span data-stu-id="52562-129">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>
* <span data-ttu-id="52562-130">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 eller senare.</span><span class="sxs-lookup"><span data-stu-id="52562-130">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 or later.</span></span> <span data-ttu-id="52562-131">Detta är tillgängligt för Windows, Mac och Linux.</span><span class="sxs-lookup"><span data-stu-id="52562-131">This is available for Windows, Mac, and Linux.</span></span>

## <a name="login-to-azure"></a><span data-ttu-id="52562-132">Logga in på Azure</span><span class="sxs-lookup"><span data-stu-id="52562-132">Login to Azure</span></span>

<span data-ttu-id="52562-133">Du kan logga in på Azure via CLI genom att skriva:</span><span class="sxs-lookup"><span data-stu-id="52562-133">To log in to Azure using the CLI, you can type:</span></span>

```azurecli
az login
```

## <a name="create-resource-group"></a><span data-ttu-id="52562-134">Skapa resursgrupp</span><span class="sxs-lookup"><span data-stu-id="52562-134">Create resource group</span></span>

<span data-ttu-id="52562-135">Skapa en resursgrupp med kommandot [az group create](/cli/azure/group#az-group-create).</span><span class="sxs-lookup"><span data-stu-id="52562-135">Create a resource group with the [az group create](/cli/azure/group#az-group-create) command.</span></span> <span data-ttu-id="52562-136">En resursgrupp i Azure är en logisk behållare där Azure-resurser distribueras och hanteras.</span><span class="sxs-lookup"><span data-stu-id="52562-136">An Azure resource group is a logical container into which Azure resources are deployed and managed.</span></span>

<span data-ttu-id="52562-137">Välj ett resursgruppnamn och fyll i platshållaren.</span><span class="sxs-lookup"><span data-stu-id="52562-137">Please select a Resource Group name and fill in the placeholder.</span></span>
<span data-ttu-id="52562-138">I följande exempel skapas en resursgrupp med namnet *<YourResourceGroupName>* på platsen *eastus*.</span><span class="sxs-lookup"><span data-stu-id="52562-138">The following example creates a resource group named *<YourResourceGroupName>* in the *eastus* location.</span></span>

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="52562-139">Resursgruppen som du nyss skapade används i hela den här självstudien.</span><span class="sxs-lookup"><span data-stu-id="52562-139">The resource group you just created is used throughout this tutorial.</span></span>

## <a name="create-an-azure-key-vault"></a><span data-ttu-id="52562-140">Skapa ett Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-140">Create an Azure Key Vault</span></span>

<span data-ttu-id="52562-141">Nu ska du skapa ett nyckelvalv i resursgruppen som du skapade i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="52562-141">Next you create a Key Vault using the resource group created in the previous step.</span></span> <span data-ttu-id="52562-142">”ContosoKeyVault” används som namn på nyckelvalvet i hela den här artikeln, men det är viktigt att poängtera att du måste använda ett unikt namn.</span><span class="sxs-lookup"><span data-stu-id="52562-142">Although “ContosoKeyVault” is used as the name for the Key Vault throughout this article, you have to use a unique name.</span></span> <span data-ttu-id="52562-143">Ange följande information:</span><span class="sxs-lookup"><span data-stu-id="52562-143">Provide the following information:</span></span>

* <span data-ttu-id="52562-144">Valvnamn – **välj ett Key Vault-namn här**.</span><span class="sxs-lookup"><span data-stu-id="52562-144">Vault name - **Select a Key Vault Name here**.</span></span>
* <span data-ttu-id="52562-145">Resursgruppsnamn – **välj ett resursgruppsnamn här**.</span><span class="sxs-lookup"><span data-stu-id="52562-145">Resource group name - **Select a Resource Group Name here**.</span></span>
* <span data-ttu-id="52562-146">Plats – **USA, östra**.</span><span class="sxs-lookup"><span data-stu-id="52562-146">The location - **East US**.</span></span>

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="52562-147">Nu är ditt Azure-konto det enda kontot med behörighet att utföra åtgärder i det nya valvet.</span><span class="sxs-lookup"><span data-stu-id="52562-147">At this point, your Azure account is the only one authorized to perform any operations on this new vault.</span></span>

## <a name="add-a-secret-to-key-vault"></a><span data-ttu-id="52562-148">Lägga till en hemlighet i Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-148">Add a secret to key vault</span></span>

<span data-ttu-id="52562-149">Vi lägger till en hemlighet för att illustrera hur detta fungerar.</span><span class="sxs-lookup"><span data-stu-id="52562-149">We're adding a secret to help illustrate how this works.</span></span> <span data-ttu-id="52562-150">Du kan lagra en SQL-anslutningssträng eller annan information som du behöver skydda men göra tillgänglig för ditt program.</span><span class="sxs-lookup"><span data-stu-id="52562-150">You could be storing a SQL connection string or any other information that you need to keep securely but make available to your application.</span></span> <span data-ttu-id="52562-151">I den här självstudiekursen kallas lösenordet **AppSecret** och lagrar värdet för **MySecret**.</span><span class="sxs-lookup"><span data-stu-id="52562-151">In this tutorial, the password will be called **AppSecret** and will store the value of **MySecret** in it.</span></span>

<span data-ttu-id="52562-152">Skriv kommandona nedan för att skapa en hemlighet i Key Vault med namnet **AppSecret** som ska lagra värdet **MySecret**:</span><span class="sxs-lookup"><span data-stu-id="52562-152">Type the commands below to create a secret in Key Vault called **AppSecret** that will store the value **MySecret**:</span></span>

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

<span data-ttu-id="52562-153">Så här visar du värdet som finns i hemligheten som oformaterad text:</span><span class="sxs-lookup"><span data-stu-id="52562-153">To view the value contained in the secret as plain text:</span></span>

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

<span data-ttu-id="52562-154">Det här kommandot visar den hemliga informationen, inklusive URI:n.</span><span class="sxs-lookup"><span data-stu-id="52562-154">This command shows the secret information including the URI.</span></span> <span data-ttu-id="52562-155">När du har slutfört de här stegen bör du ha en URI till en hemlighet i Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="52562-155">After completing these steps, you should have a URI to a secret in an Azure Key Vault.</span></span> <span data-ttu-id="52562-156">Anteckna den här informationen.</span><span class="sxs-lookup"><span data-stu-id="52562-156">Write this information down.</span></span> <span data-ttu-id="52562-157">Du behöver den senare.</span><span class="sxs-lookup"><span data-stu-id="52562-157">You need it in a later step.</span></span>

## <a name="clone-the-repo"></a><span data-ttu-id="52562-158">Klona lagringsplatsen</span><span class="sxs-lookup"><span data-stu-id="52562-158">Clone the Repo</span></span>

<span data-ttu-id="52562-159">Klona lagringsplatsen för att skapa en lokal kopia så att du kan redigera källan genom att köra följande kommando:</span><span class="sxs-lookup"><span data-stu-id="52562-159">Clone the repo in order to make a local copy for you to edit the source by running the following command:</span></span>

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

<span data-ttu-id="52562-160">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="52562-160">::: zone pivot="nodejs"</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="52562-161">Installera beroenden</span><span class="sxs-lookup"><span data-stu-id="52562-161">Install dependencies</span></span>

<span data-ttu-id="52562-162">Här installera vi beroendena.</span><span class="sxs-lookup"><span data-stu-id="52562-162">Here we install the dependencies.</span></span> <span data-ttu-id="52562-163">Kör följande kommandon: cd key-vault-node-quickstart npm install</span><span class="sxs-lookup"><span data-stu-id="52562-163">Run the following commands cd key-vault-node-quickstart npm install</span></span>

<span data-ttu-id="52562-164">I det här projektet används 2 Node-moduler:</span><span class="sxs-lookup"><span data-stu-id="52562-164">This project used 2 node modules:</span></span>

* [<span data-ttu-id="52562-165">ms-rest-azure</span><span class="sxs-lookup"><span data-stu-id="52562-165">ms-rest-azure</span></span>](https://www.npmjs.com/package/ms-rest-azure) 
* [<span data-ttu-id="52562-166">azure-keyvault</span><span class="sxs-lookup"><span data-stu-id="52562-166">azure-keyvault</span></span>](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="52562-167">Publicera webbappen till Azure</span><span class="sxs-lookup"><span data-stu-id="52562-167">Publish the web application to Azure</span></span>

<span data-ttu-id="52562-168">Nedan beskrivs de få steg som krävs</span><span class="sxs-lookup"><span data-stu-id="52562-168">Below are the few steps we need to do</span></span>

* <span data-ttu-id="52562-169">Det första steget är att skapa en [Azure App Service](https://azure.microsoft.com/services/app-service/)-plan.</span><span class="sxs-lookup"><span data-stu-id="52562-169">The 1st step is to create a [Azure App Service](https://azure.microsoft.com/services/app-service/) Plan.</span></span> <span data-ttu-id="52562-170">Du kan lagra flera webbappar i den här planen.</span><span class="sxs-lookup"><span data-stu-id="52562-170">You can store multiple web apps in this plan.</span></span>

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* <span data-ttu-id="52562-171">Därefter skapar vi en webbapp.</span><span class="sxs-lookup"><span data-stu-id="52562-171">Next we create a web app.</span></span> <span data-ttu-id="52562-172">I följande exempel ersätter du <app_name> med ett globalt, unikt appnamn (giltiga tecken är a-z, 0-9 och -).</span><span class="sxs-lookup"><span data-stu-id="52562-172">In the following example, replace <app_name> with a globally unique app name (valid characters are a-z, 0-9, and -).</span></span> <span data-ttu-id="52562-173">Körningen är inställd på NODE|6.9.</span><span class="sxs-lookup"><span data-stu-id="52562-173">The runtime is set to NODE|6.9.</span></span> <span data-ttu-id="52562-174">Kör az webapp list-runtimes om du vill visa alla körningar</span><span class="sxs-lookup"><span data-stu-id="52562-174">To see all supported runtimes, run az webapp list-runtimes</span></span>

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    <span data-ttu-id="52562-175">När webbappen har skapats visar Azure CLI utdata liknande den i följande exempel:</span><span class="sxs-lookup"><span data-stu-id="52562-175">When the web app has been created, the Azure CLI shows output similar to the following example:</span></span>

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
    <span data-ttu-id="52562-176">Gå till den nya webbappen, så bör du se en fungerande webbapp.</span><span class="sxs-lookup"><span data-stu-id="52562-176">Browse to your newly created web app and you should see a functioning web app.</span></span> <span data-ttu-id="52562-177">Ersätt <app_name> med ett unikt appnamn.</span><span class="sxs-lookup"><span data-stu-id="52562-177">Replace <app_name> with a unique app name.</span></span>

    ```text
    http://<app name>.azurewebsites.net
    ```
    <span data-ttu-id="52562-178">Kommandot ovan skapar även en Git-aktiverad app som gör att du kan distribuera till Azure från din lokala git-lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="52562-178">The above command also creates a Git-enabled app which allows you to deploy to azure from your local git.</span></span> 
    <span data-ttu-id="52562-179">Den lokala git-lagringsplatsen konfigureras med URL:en ”https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git”</span><span class="sxs-lookup"><span data-stu-id="52562-179">Local git is configured with url of 'https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git'</span></span>

* <span data-ttu-id="52562-180">Skapa en distributionsanvändare. När det föregående kommandot har slutförts kan du lägga till en Azure-fjärranslutning till din lokala Git-lagringsplats.</span><span class="sxs-lookup"><span data-stu-id="52562-180">Create a deployment user After the previous command is completed you can add add an Azure remote to your local Git repository.</span></span> <span data-ttu-id="52562-181">Ersätt <url> med URL:en för den fjärranslutna Git-lagringsplats som du fick från Aktivera Git för din app.</span><span class="sxs-lookup"><span data-stu-id="52562-181">Replace <url> with the URL of the Git remote that you got from Enable Git for your app.</span></span>

    ```bash
    git remote add azure <url>
    ```
    
<span data-ttu-id="52562-182">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="52562-182">::: zone-end</span></span>

<span data-ttu-id="52562-183">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="52562-183">::: zone pivot="dotnet"</span></span>
## <a name="open-and-edit-the-solution"></a><span data-ttu-id="52562-184">Öppna och redigera lösningen</span><span class="sxs-lookup"><span data-stu-id="52562-184">Open and edit the solution</span></span>

<span data-ttu-id="52562-185">Redigera filen program.cs för att köra exemplet med namnet på ditt specifika nyckelvalvsnamn:</span><span class="sxs-lookup"><span data-stu-id="52562-185">Edit the program.cs file to run the sample with your specific key vault name:</span></span>

1. <span data-ttu-id="52562-186">Bläddra till mappen key-vault-dotnet-core-quickstart.</span><span class="sxs-lookup"><span data-stu-id="52562-186">Browse to the folder key-vault-dotnet-core-quickstart.</span></span>
2. <span data-ttu-id="52562-187">Öppna filen key-vault-dotnet-core-quickstart.sln i Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="52562-187">Open the key-vault-dotnet-core-quickstart.sln file in Visual Studio 2017.</span></span>
3. <span data-ttu-id="52562-188">Öppna filen Program.cs och uppdatera platshållaren *YourKeyVaultName* med namnet på det nyckelvalv som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="52562-188">Open the Program.cs file and update the placeholder *YourKeyVaultName* with the name of your key vault that you created earlier.</span></span>

<span data-ttu-id="52562-189">Den här lösningen använder NuGet-biblioteken [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) och [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).</span><span class="sxs-lookup"><span data-stu-id="52562-189">This solution uses [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) and [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet libraries.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="52562-190">Kör appen</span><span class="sxs-lookup"><span data-stu-id="52562-190">Run the app</span></span>

<span data-ttu-id="52562-191">På huvudmenyn för Visual Studio 2017 väljer du **Felsökning** > **Starta** utan felsökning.</span><span class="sxs-lookup"><span data-stu-id="52562-191">From the main menu of Visual Studio 2017, select **Debug** > **Start** without debugging.</span></span> <span data-ttu-id="52562-192">När webbläsaren visas går du till sidan **Om**.</span><span class="sxs-lookup"><span data-stu-id="52562-192">When the browser appears, go to the **About** page.</span></span> <span data-ttu-id="52562-193">Värdet för **AppSecret** visas.</span><span class="sxs-lookup"><span data-stu-id="52562-193">The value for **AppSecret** is displayed.</span></span>

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="52562-194">Publicera webbappen till Azure</span><span class="sxs-lookup"><span data-stu-id="52562-194">Publish the web application to Azure</span></span>

<span data-ttu-id="52562-195">Publicera den här appen till Azure för att se den live som en webbapp och se att du kan hämta det hemliga värdet:</span><span class="sxs-lookup"><span data-stu-id="52562-195">Publish this app to Azure to see it live as a web app, and to see that you can fetch the secret value:</span></span>

1. <span data-ttu-id="52562-196">I Visual Studio väljer du projektet **key-vault-dotnet-core-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="52562-196">In Visual Studio, select the **key-vault-dotnet-core-quickstart** project.</span></span>
2. <span data-ttu-id="52562-197">Välj **Publicera** > **Start**.</span><span class="sxs-lookup"><span data-stu-id="52562-197">Select **Publish** > **Start**.</span></span>
3. <span data-ttu-id="52562-198">Skapa en ny **App Service** och välj sedan **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="52562-198">Create a new **App Service**, and then select **Publish**.</span></span>
4. <span data-ttu-id="52562-199">Ändra namnet på appen till **keyvaultdotnetcorequickstart**.</span><span class="sxs-lookup"><span data-stu-id="52562-199">Change the app name to **keyvaultdotnetcorequickstart**.</span></span>
5. <span data-ttu-id="52562-200">Välj **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="52562-200">Select **Create**.</span></span>

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]
<span data-ttu-id="52562-201">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="52562-201">::: zone-end</span></span>

## <a name="enable-managed-service-identities"></a><span data-ttu-id="52562-202">Aktivera hanterade tjänstidentiteter</span><span class="sxs-lookup"><span data-stu-id="52562-202">Enable managed service identities</span></span>

<span data-ttu-id="52562-203">Azure Key Vault är ett sätt att lagra autentiseringsuppgifter samt andra nycklar och hemligheter på ett säkert sätt, men din kod måste autentiseras till Azure Key Vault för att kunna hämta dem.</span><span class="sxs-lookup"><span data-stu-id="52562-203">Azure Key Vault provides a way to securely store credentials and other keys and secrets, but your code needs to authenticate to Azure Key Vault to retrieve them.</span></span> <span data-ttu-id="52562-204">Hanterad tjänstidentitet gör det här enklare genom att ge Azure-tjänsterna en automatiskt hanterad identitet i Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="52562-204">Managed Service Identity makes this easier by giving Azure services an automatically managed identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="52562-205">Du kan använda den här identiteten för att autentisera till alla tjänster som stöder Azure AD-autentisering, inklusive Key Vault, utan att behöva ha några autentiseringsuppgifter i koden.</span><span class="sxs-lookup"><span data-stu-id="52562-205">You can use this identity to authenticate to any service that supports Azure AD authentication, including Key Vault, without having any credentials in your code.</span></span>

1. <span data-ttu-id="52562-206">Gå tillbaka till Azure CLI.</span><span class="sxs-lookup"><span data-stu-id="52562-206">Return to the Azure CLI.</span></span>
2. <span data-ttu-id="52562-207">Kör kommandot assign-identity för att skapa identiteten för det här programmet:</span><span class="sxs-lookup"><span data-stu-id="52562-207">Run the assign-identity command to create the identity for this application:</span></span>

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
><span data-ttu-id="52562-208">Kommandot i denna proceduren fungerar på samma sätt som när du går till portalen och väljer **På** för **Hanterad tjänstidentitet** i egenskaperna för webbprogrammet.</span><span class="sxs-lookup"><span data-stu-id="52562-208">The command in this procedure is the equivalent of going to the portal and switching **Managed service identity** to **On** in the web application properties.</span></span>

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a><span data-ttu-id="52562-209">Tilldela behörigheter till ditt program att läsa hemligheter från Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-209">Assign permissions to your application to read secrets from Key Vault</span></span>

<span data-ttu-id="52562-210">Anteckna utdata när du publicerar programmet till Azure.</span><span class="sxs-lookup"><span data-stu-id="52562-210">Make a note of the output when you publish the application to Azure.</span></span> <span data-ttu-id="52562-211">Det ska vara i formatet:</span><span class="sxs-lookup"><span data-stu-id="52562-211">It should be of the format:</span></span>

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

<span data-ttu-id="52562-212">Kör sedan det här kommandot med namnet på ditt nyckelvalv och värdet för **PrincipalId**:</span><span class="sxs-lookup"><span data-stu-id="52562-212">Then, run this command by using the name of your key vault and the value of **PrincipalId**:</span></span>

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

<span data-ttu-id="52562-213">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="52562-213">::: zone pivot="nodejs"</span></span>
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a><span data-ttu-id="52562-214">Distribuera Node-appen till Azure och hämta det hemliga värdet</span><span class="sxs-lookup"><span data-stu-id="52562-214">Deploy the Node App to Azure and retrieve the secret value</span></span>

<span data-ttu-id="52562-215">Nu är allt konfigurerat.</span><span class="sxs-lookup"><span data-stu-id="52562-215">Now that everything is set.</span></span> <span data-ttu-id="52562-216">Distribuera appen till Azure genom att köra följande kommando</span><span class="sxs-lookup"><span data-stu-id="52562-216">Run the following command to deploy the app to Azure</span></span>

```bash
git push azure master
```

<span data-ttu-id="52562-217">När du har gjort det och går till https://<app_name>.azurewebsites.net kan du se det hemliga värdet.</span><span class="sxs-lookup"><span data-stu-id="52562-217">After this when you browse https://<app_name>.azurewebsites.net you can see the secret value.</span></span>
<span data-ttu-id="52562-218">Kontrollera att du ersatte namnet <YourKeyVaultName> med namnet på ditt valv</span><span class="sxs-lookup"><span data-stu-id="52562-218">Make sure that you replaced the name <YourKeyVaultName> with your vault name</span></span>

<span data-ttu-id="52562-219">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="52562-219">::: zone-end</span></span>

<span data-ttu-id="52562-220">::: zone pivot="dotnet" Nu när du kör programmet bör ditt hemliga värde hämtas.</span><span class="sxs-lookup"><span data-stu-id="52562-220">::: zone pivot="dotnet" Now when you run the application, you should see your secret value retrieved.</span></span>
<span data-ttu-id="52562-221">::: zone-end</span><span class="sxs-lookup"><span data-stu-id="52562-221">::: zone-end</span></span>

## <a name="next-steps"></a><span data-ttu-id="52562-222">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="52562-222">Next steps</span></span>

<span data-ttu-id="52562-223">::: zone pivot="nodejs"</span><span class="sxs-lookup"><span data-stu-id="52562-223">::: zone pivot="nodejs"</span></span>
* [<span data-ttu-id="52562-224">Startsida för Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-224">Azure Key Vault Home Page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="52562-225">Dokumentation om Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-225">Azure Key Vault Documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="52562-226">Azure SDK för Node</span><span class="sxs-lookup"><span data-stu-id="52562-226">Azure SDK For Node</span></span>](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)
* <span data-ttu-id="52562-227">[Azure REST API-referens](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="52562-227">[Azure REST API Reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>

<span data-ttu-id="52562-228">::: zone pivot="dotnet"</span><span class="sxs-lookup"><span data-stu-id="52562-228">::: zone pivot="dotnet"</span></span>
* [<span data-ttu-id="52562-229">Startsida för Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-229">Azure Key Vault home page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="52562-230">Dokumentation om Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="52562-230">Azure Key Vault documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="52562-231">Azure SDK för .NET</span><span class="sxs-lookup"><span data-stu-id="52562-231">Azure SDK For .NET</span></span>](https://github.com/Azure/azure-sdk-for-net)
* <span data-ttu-id="52562-232">[Azure REST API-referens](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span><span class="sxs-lookup"><span data-stu-id="52562-232">[Azure REST API reference](https://docs.microsoft.com/rest/api/keyvault/) ::: zone-end</span></span>
