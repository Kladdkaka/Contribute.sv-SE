<span data-ttu-id="93d17-101">Med kommentarsautomatisering kan användare på läsnivå (användare som inte har skrivbehörighet i en lagringsplats) utföra en åtgärd på skrivnivå genom att tilldela en pull-begäran rätt etikett.</span><span class="sxs-lookup"><span data-stu-id="93d17-101">Comment automation enables read-level users (users who don't have write permissions in a repo) to perform a write-level action, by assigning the appropriate label to a pull request.</span></span> <span data-ttu-id="93d17-102">Om du arbetar i en lagringsplats där kommentarautomatisering har implementeras kan du använda hashtaggkommentarerna i tabellen nedan för att tilldela etiketter, ändra etiketter eller stänga en pull-begäran.</span><span class="sxs-lookup"><span data-stu-id="93d17-102">If you are working in a repository where comment automation has been implemented, use the hashtag comments listed in the following table to assign labels, change labels, or close a pull request.</span></span> <span data-ttu-id="93d17-103">Microsoft-anställda meddelas även via e-post om granskning och slutgodkännande av pull-begäranden i offentliga lagringsplatser när ändringar föreslås i artiklar där du står som författare.</span><span class="sxs-lookup"><span data-stu-id="93d17-103">Microsoft employees will also be notified via e-mail for review and sign-off of public repository PRs, whenever changes are proposed to articles for which you are the author.</span></span>


| <span data-ttu-id="93d17-104">Hashtaggkommentar</span><span class="sxs-lookup"><span data-stu-id="93d17-104">Hashtag comment</span></span> | <span data-ttu-id="93d17-105">Vad den gör</span><span class="sxs-lookup"><span data-stu-id="93d17-105">What it does</span></span> | <span data-ttu-id="93d17-106">Lagringsplatsens tillgänglighet</span><span class="sxs-lookup"><span data-stu-id="93d17-106">Repo availability</span></span> |
| --- | --- | --- |
| <span data-ttu-id="93d17-107">#sign-off</span><span class="sxs-lookup"><span data-stu-id="93d17-107">#sign-off</span></span> |<span data-ttu-id="93d17-108">När artikelförfattaren skriver kommentaren **#sign-off** i kommentarsströmmen tilldelas etiketten **ready-to-merge** (klar att slås samman).</span><span class="sxs-lookup"><span data-stu-id="93d17-108">When the author of an article types the **#sign-off** comment in the comment stream, the **ready-to-merge** label is assigned.</span></span> <span data-ttu-id="93d17-109">Den här etiketten låter granskare i lagringsplatsen veta när en pull-begäran är klar för granskning/sammanslagning.</span><span class="sxs-lookup"><span data-stu-id="93d17-109">This label lets the reviewers in the repo know when a pull request is ready for review/merge.</span></span> |<span data-ttu-id="93d17-110">Offentlig och privat</span><span class="sxs-lookup"><span data-stu-id="93d17-110">Public and private</span></span> |
| <span data-ttu-id="93d17-111">#sign-off</span><span class="sxs-lookup"><span data-stu-id="93d17-111">#sign-off</span></span> |<span data-ttu-id="93d17-112">Om en deltagare som *inte* är angiven som författare försöker avsluta en offentlig pull-begäran med hjälp av kommentaren **#sign-off** skapas ett meddelande i pull-begäran som anger att endast författaren kan tilldela den här etiketten.</span><span class="sxs-lookup"><span data-stu-id="93d17-112">If a contributor who is *not* the listed author tries to sign off on a public pull request by using the **#sign-off** comment, a message is written to the pull request indicating that only the author can assign the label.</span></span> |<span data-ttu-id="93d17-113">Offentlig</span><span class="sxs-lookup"><span data-stu-id="93d17-113">Public</span></span> |
| <span data-ttu-id="93d17-114">#hold-off</span><span class="sxs-lookup"><span data-stu-id="93d17-114">#hold-off</span></span> |<span data-ttu-id="93d17-115">Författare kan skriva **hold-off #** i en kommentar till en pull-begäran för att ta bort etiketten **ready-to-merge** – om de ändrar sig eller har gjort fel.</span><span class="sxs-lookup"><span data-stu-id="93d17-115">Authors can type **#hold-off** in a PR comment to remove the **ready-to-merge** label--in case they change their mind or make a mistake.</span></span> <span data-ttu-id="93d17-116">I en privat lagringsplats tilldelas etiketten **do-not-merge** (slå inte samman).</span><span class="sxs-lookup"><span data-stu-id="93d17-116">In the private repo, this assigns the **do-not-merge** label.</span></span> |<span data-ttu-id="93d17-117">Offentlig och privat</span><span class="sxs-lookup"><span data-stu-id="93d17-117">Public and private</span></span> |
| <span data-ttu-id="93d17-118">#please-close</span><span class="sxs-lookup"><span data-stu-id="93d17-118">#please-close</span></span> |<span data-ttu-id="93d17-119">Författare kan skriva **#please-close** i kommentarsströmmen för att stänga pull-begäran om de inte vill att ändringarna ska slås samman.</span><span class="sxs-lookup"><span data-stu-id="93d17-119">Authors can type **#please-close** in the comment stream to close the pull request if they decide not to have the changes merged.</span></span> |<span data-ttu-id="93d17-120">Offentlig</span><span class="sxs-lookup"><span data-stu-id="93d17-120">Public</span></span> |