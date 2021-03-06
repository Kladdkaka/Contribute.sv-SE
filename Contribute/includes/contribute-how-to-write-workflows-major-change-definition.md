 - **Göra ett stort bidrag**. Du kan till exempel göra bidrag (tillägg, ändringar eller borttagningar) som sträcker sig över flera artiklar och som måste skickas in och testas som en arbetsenhet i en enda pull-begäran. 
 - **Skapa och publicera en ny artikel**, som normalt kräver ett stabilare lokalt redigeringsprogram. 
 - **Lägga till nya bilder eller uppdatera bilder**. Detta kräver normalt att du samtidigt skapar en ny `media`-underkatalog, bildfiler, uppdateringar av bildlänkar i artiklar och förhandsgranskar Markdown-filer i ett lokalt redigeringsprogram för att testa bildåtergivning.
 - **Uppdatera en artikel i flera dagar innan publicering sker**. I dessa fall måste du normalt genomföra vanlig integrering av andra ändringar som sker i huvudgrenen. Den här integreringen är enklare att utföra via Git Bash och lokal redigering. Du löper även risk att förlora redigeringarna om du gör detta via GitHub-gränssnittet och väntar innan du skickar ändringarna.
 - **Göra löpande uppdateringar av samma artikel efter att en pull-begäran har öppnats** (såvida inte du känner dig bekväm med att göra detta via GitHub-gränssnittet). Om du använder GitHub-gränssnittet finns det risk för att skapa flera utestående pull-begäran för samma fil, vilket kan leda till konflikter mellan dessa. 