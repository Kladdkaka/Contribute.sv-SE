## <a name="pull-request-processing"></a>Bearbetning av pull-begäran

Föregående avsnitt gick igenom processen för att skicka in föreslagna ändringar genom att paketera dem i en ny pull-begäran (PR) som läggs till i mållagrets kö för pull-begäranden. En pull-begäran aktiverar GitHubs samarbetsmodell genom att be om att ändringarna från arbetsgrenen ska "dras" och sammanfogas i en annan gren. I de flesta fall är den andra grenen standard/huvud i huvudlagret.

### <a name="validation"></a>Validering

Innan din pull-begäran kan sammanfogas till målgrenen kan det vara ett krav att den genomgår en eller flera valideringsprocesser för pull-begäranden. Valideringsprocesserna kan variera beroende på de föreslagna ändringarnas omfattning och mållagrets regler. När pull-begäran har skickats kan du förvänta dig att en eller flera av följande saker händer:

- **Sammanfogningsmöjlighet:** Ett baslinjetest för sammanfogningsmöjlighet med GitHub utförs först för att verifiera om de föreslagna ändringarna i grenen har någon konflikt med målgrenen. Om pull-begäran visar att testet misslyckades måste du kontrollera innehållet som orsakar sammanfogningskonflikten innan bearbetningen kan fortsätta.
- **CLA:** Om du bidrar till ett offentligt lager och inte är Microsoft-medarbetare kan du, beroende på de föreslagna ändringarnas omfattning, bli ombedd att fylla i ett kort licensavtal för bidrag (CLA) första gången du skickar en pull-begäran till det lagret. När steget med det korta licensavtalet för bidrag (CLA) är slutfört bearbetas pull-begäran.
- **Märkning:** Etiketter används automatiskt på pull-begäran för att ange dess status när den genomgår valideringsarbetsflödet. Nya pull-begäranden kan till exempel få etiketten "do-not-merge" automatiskt, som visar att pull-begäran ännu inte har slutfört stegen för validering, granskning och signering.
- **Validering och version**: Kontrollerar automatiskt om ändringarna godkänns i valideringstesterna. Valideringstesterna kan resultera i varningar eller fel som kräver att du gör ändringar i en eller flera filer i pull-begäran innan den kan sammanfogas. Resultaten av valideringstesterna läggs till som en kommentar i pull-begäran så att du kan granska dem. De kan även skickas till dig via e-post.
- **Mellanlagring:** De artikelsidor som påverkas av ändringarna distribueras automatiskt till en mellanlagringsmiljö för granskning efter lyckad validering och version. Granska URL:erna som visas i pull-begärans kommentar.
- **Automatisk sammanfogning:** Pull-begäran kan sammanfogas automatiskt om den godkänns vid valideringstestning och uppfyller vissa kriterier. I det här fallet behöver du inte utföra några ytterligare åtgärder.

### <a name="review-and-sign-off"></a>Granskning och signering

När all PR-bearbetning har slutförts granskar du resultaten (PR-kommentarer, URL:er för förhandsgranskning osv.) för att fastställa om ytterligare ändringar av filerna krävs innan du signerar för sammanfogning. Om granskaren av PR har granskat pull-begäran kan denna person även tillhandahålla feedback via kommentarer om det finns kvarstående problem/frågor som måste lösas före sammanfogningen.

[!INCLUDE[contribute-how-to-pull-requests-apex-automation.md](contribute-how-to-pull-requests-apex-automation.md)]

När pull-begäran är fri från problem och signerad sammanfogas dina ändringar med den överordnade grenen och pull-begäran avslutas.

### <a name="publishing"></a>Publicering

Kom ihåg att pull-begäran måste sammanfogas av en PR-granskare innan ändringarna kan inkluderas i nästa schemalagda publiceringskörning. Pull-begäranden granskas/sammanfogas i den ordning som de skickades in. Om pull-begäran kräver sammanfogning för en specifik publiceringskörning måste du samarbeta med PR-granskaren i förväg för att säkerställa att sammanfogningen sker före publicering.

När bidragen har godkänts och sammanfogats hämtas de av publiceringsprocessen för docs.microsoft.com. Publiceringstiderna kan variera beroende på vilket team som hanterar lagret som du bidrar till. Artiklar som publiceras under följande sökvägar distribueras normalt ca 10:30 och 15:30 stillahavstid, måndag–fredag:

- https://docs.microsoft.com/azure/
- https://docs.microsoft.com/aspnet/
- https://docs.microsoft.com/dotnet/
- https://docs.microsoft.com/enterprise-mobility-security

Det kan ta upp till 45 minuter innan artiklar syns online efter publicering. När artikeln har publicerats kan du kontrollera ändringarna på den lämpliga URL:en: `https://docs.microsoft.com/<path-to-your-article-without-the-md-extension>`.
