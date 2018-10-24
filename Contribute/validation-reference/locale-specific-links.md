# <a name="locale-specific-links"></a>Språkspecifika länkar

Nationalitetskoder, till exempel `en-us`, får inte ingå i länkar till vissa Microsoft-webbplatser. Om du lägger in en nationalitetskod i en länk till innehåll på engelska tas den även med i lokaliserade länkar, vilket ger en dålig lokaliseringsupplevelse. Om en länk i lokaliserat innehåll på tyska innehåller `en-us` länkas tyska användare till den engelska artikeln, även om det finns en tysk version.

Ta bort nationalitetskoder från länkar till Microsoft-webbplatser. Följande är ett exempel.

Före:

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

Efter:

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

Följande webbplatser omfattas av den här valideringen:

- azure.microsoft.com
- docs.microsoft.com
- msdn.microsoft.com
- technet.microsoft.com