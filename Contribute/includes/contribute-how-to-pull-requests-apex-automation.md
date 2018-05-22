Med kommentarsautomatisering kan användare på läsnivå (användare som inte har skrivbehörighet i en lagringsplats) utföra en åtgärd på skrivnivå genom att tilldela en pull-begäran rätt etikett. Om du arbetar i en lagringsplats där kommentarautomatisering har implementeras kan du använda hashtaggkommentarerna i tabellen nedan för att tilldela etiketter, ändra etiketter eller stänga en pull-begäran. Microsoft-anställda meddelas även via e-post om granskning och slutgodkännande av pull-begäranden i offentliga lagringsplatser när ändringar föreslås i artiklar där du står som författare.


| Hashtaggkommentar | Vad den gör | Lagringsplatsens tillgänglighet |
| --- | --- | --- |
| #sign-off |När artikelförfattaren skriver kommentaren **#sign-off** i kommentarsströmmen tilldelas etiketten **ready-to-merge** (klar att slås samman). Den här etiketten låter granskare i lagringsplatsen veta när en pull-begäran är klar för granskning/sammanslagning. |Offentlig och privat |
| #sign-off |Om en deltagare som *inte* är angiven som författare försöker avsluta en offentlig pull-begäran med hjälp av kommentaren **#sign-off** skapas ett meddelande i pull-begäran som anger att endast författaren kan tilldela den här etiketten. |Offentlig |
| #hold-off |Författare kan skriva **hold-off #** i en kommentar till en pull-begäran för att ta bort etiketten **ready-to-merge** – om de ändrar sig eller har gjort fel. I en privat lagringsplats tilldelas etiketten **do-not-merge** (slå inte samman). |Offentlig och privat |
| #please-close |Författare kan skriva **#please-close** i kommentarsströmmen för att stänga pull-begäran om de inte vill att ändringarna ska slås samman. |Offentlig |
