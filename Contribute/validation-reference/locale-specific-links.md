# <a name="locale-specific-links"></a><span data-ttu-id="5caee-101">Språkspecifika länkar</span><span class="sxs-lookup"><span data-stu-id="5caee-101">Locale-specific links</span></span>

<span data-ttu-id="5caee-102">Nationalitetskoder, till exempel `en-us`, får inte ingå i länkar till vissa Microsoft-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="5caee-102">Locale codes, such as `en-us`, should not be included in links to certain Microsoft sites.</span></span> <span data-ttu-id="5caee-103">Om du lägger in en nationalitetskod i en länk till innehåll på engelska tas den även med i lokaliserade länkar, vilket ger en dålig lokaliseringsupplevelse.</span><span class="sxs-lookup"><span data-stu-id="5caee-103">If you include a locale code in a link in English content, it will also be included in localized links, which leads to a bad localized experience.</span></span> <span data-ttu-id="5caee-104">Om en länk i lokaliserat innehåll på tyska innehåller `en-us` länkas tyska användare till den engelska artikeln, även om det finns en tysk version.</span><span class="sxs-lookup"><span data-stu-id="5caee-104">For example, if a link in German localized content includes `en-us`, German customers will find themselves linking to the English article, even if a German version is available.</span></span>

<span data-ttu-id="5caee-105">Ta bort nationalitetskoder från länkar till Microsoft-webbplatser.</span><span class="sxs-lookup"><span data-stu-id="5caee-105">Remove locale codes from links to Microsoft sites.</span></span> <span data-ttu-id="5caee-106">Följande är ett exempel.</span><span class="sxs-lookup"><span data-stu-id="5caee-106">The following is an example.</span></span>

<span data-ttu-id="5caee-107">Före:</span><span class="sxs-lookup"><span data-stu-id="5caee-107">Before:</span></span>

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="5caee-108">Efter:</span><span class="sxs-lookup"><span data-stu-id="5caee-108">After:</span></span>

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

<span data-ttu-id="5caee-109">Följande webbplatser omfattas av den här valideringen:</span><span class="sxs-lookup"><span data-stu-id="5caee-109">The following sites are in scope for this validation:</span></span>

- <span data-ttu-id="5caee-110">azure.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5caee-110">azure.microsoft.com</span></span>
- <span data-ttu-id="5caee-111">docs.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5caee-111">docs.microsoft.com</span></span>
- <span data-ttu-id="5caee-112">msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5caee-112">msdn.microsoft.com</span></span>
- <span data-ttu-id="5caee-113">technet.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5caee-113">technet.microsoft.com</span></span>