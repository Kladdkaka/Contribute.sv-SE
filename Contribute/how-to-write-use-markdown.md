---
title: Använda Markdown för att skriva i Docs
description: Den här artikeln innehåller grundläggande information och referensinformation för Markdown-språket som används för att skriva artiklar på docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 07/13/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 041398361aef90c44bdf3a0dad4aaa2d40a38289
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/23/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a>Använda Markdown för att skriva i Docs

Docs.microsoft.com-artiklar skrivs i ett förenklat märkspråk som heter [Markdown](https://daringfireball.net/projects/markdown/) vilket är lätt att läsa och lätt att lära sig. På grund av detta har det snabbt blivit en industristandard.

Eftersom Docs-innehåll lagras på GitHub används en överordnad uppsättning av Markdown som kallas [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/) som ger ytterligare funktioner för vanliga formateringsbehov. Open Publishing Services (OPS) implementerar dessutom Markdig Markdown Parser. Markdig är starkt kompatibelt med GitHub Flavored Markdown (GFM), vilket möjliggör Docs-specifika funktioner.

* Markdig är en snabb, kraftfull, CommonMark-kompatibel, utökningsbar Markdown-processor för .NET.
* https://github.com/lunet-io/markdig
* Bättre communitysupport
* Bättre standardsupport

## <a name="markdown-basics"></a>Grunder för Markdown

### <a name="headings"></a>Sidhuvud

Använd fyrkantstecknet (#) för att skapa en rubrik:

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a>Fet och kursiv stil

Använd två asterisker runt textsträngen för att formatera text som **fet**:

```markdown
    This text is **bold**.
```

Använd en asterisk runt textsträngen för att formatera text som *kursiv*:

```markdown
    This text is *italic*.
```

Använd tre asterisker runt textsträngen för att formatera text som både ***fet och kursiv***:

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a>Listor

#### <a name="unordered-list"></a>Osorterad lista

Du kan använda asterisker eller tankstreck för att formatera en punktlista eller en osorterad lista. Till exempel, följande Markdown:

```markdown
- List item 1
- List item 2
- List item 3
```

återges som:

- Listobjekt 1
- Listobjekt 2
- Listobjekt 3

Om du vill bädda in en lista i en annan lista skapar du ett indrag före den underordnade listans objekt. Till exempel, följande Markdown:

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

återges som:

- Listobjekt 1
  - Listobjekt A
  - Listobjekt B
- Listobjekt 2

#### <a name="ordered-list"></a>Ordnad lista

Du kan använda motsvarande siffror för att formatera en ordnad/stegvis lista. Till exempel, följande Markdown:

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

återges som:

1. Första instruktionen
2. Andra instruktionen
3. Tredje instruktionen

Om du vill bädda in en lista i en annan lista skapar du ett indrag före den underordnade listans objekt. Till exempel, följande Markdown:

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

återges som:

1. Första instruktionen
    1. Underinstruktion
    2. Underinstruktion
2. Andra instruktionen

### <a name="tables"></a>Tabeller

Tabeller är inte del av stommen i Markdown-specifikationerna, men de stöds av GFM. Du kan skapa tabeller med hjälp av tecknen lodrätt streck (|) och bindestreck (-). Bindestreck skapar varje kolumnrubrik medan lodräta streck separerar varje kolumn. Inkludera ett blankstreck framför tabellen så att den renderas korrekt.

Till exempel, följande Markdown:

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

återges som:

| Roligt                  | Med                 | Tabeller          |
| :------------------- | -------------------: |:---------------:|
| vänsterjusterad kolumn  | högerjusterad kolumn | centrerad kolumn |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |

Mer information om att skapa tabeller finns här:

- [Tabellhanteringsfunktionen](#table-wrapping) i Markdig kan vara användbar vid formatering av breda tabeller
- GitHubs [Organisera information med tabeller](https://help.github.com/articles/organizing-information-with-tables/)
- Webbappen [Markdown-tabellgenerator](https://www.tablesgenerator.com/markdown_tables)
- [Adam Pritchards lathund för Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)
- [Michel Fortins extra om Markdown](https://michelf.ca/projects/php-markdown/extra/#table)
- [Konvertera HTML-tabeller till Markdown](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a>Länkar

Markdown-syntaxen för en intern länk består av en `[link text]`-del, som består av texten som länkas, följt av `(file-name.md)`-delen, vilket är den länkade webbadressen eller filnamnet:

 `[link text](file-name.md)`

För mer information om länkar, se:

- [Markdown-syntaxguiden](https://daringfireball.net/projects/markdown/syntax#link) för information om Markdowns stöd för baslänkning.
- Avsnittet [Länkar](how-to-write-links.md) i den här anvisningen för information om mer länkningssyntax som Markdig erbjuder.

### <a name="code-snippets"></a>Kodfragment

Markdown stöder placering av interna kodfragment i en mening samt avskilda kodfragment mellan meningar. Mer information finns här:

- [Markdowns inbyggda stöd för kodblock](https://daringfireball.net/projects/markdown/syntax#precode)
- [GFM:s stöd för avskild kod och syntaxmarkering](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Genom att skilja kodfragment är det lätt att markera syntaxen för dessa. Det allmänna formatet för skilda kodblock är:

    ```alias
    ...
    your code goes in here
    ...
    ```

Alias efter de tre första accenttecknen'`' definierar vilken syntaxmarkering som ska användas. Följande är en lista över vanliga programmeringsspråk i Docs-innehåll och motsvarande etikett:

Dessa språk har support för eget namn och de flesta har språkmarkering.

|Namn|Markdown-etikett|
|-----|-------|
|.NET Console|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|AzCopy|azcopy|
|Azure CLI|azurecli|
|Azure PowerShell|azurepowershell|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|CSHTML|cshtml|
|DAX|dax|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|Power Apps Formula|powerappsfl|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|VSTS CLI|vstscli|
|XAML|xaml|
|XML|xml|

#### <a name="example-c"></a>Exempel: C\#

__Markdown__

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

__Rendera__

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a>Exempel: SQL

__Markdown__

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

__Rendera__

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a>OPS-anpassade Markdown-förlängningar

> [!NOTE]
> Open Publishing Services (OPS) implementerar Markdig Parser för Markdown, som är mycket kompatibel med GitHub Flavored Markdown (GFM). Markdig lägger till vissa ytterligare funktioner via Markdown-tillägg. Utvalda artiklar från den fullständiga OPS-redigeringsguiden ingår till exempel i den här handboken som referens. (Se till exempel ”Markdig- och Markdown-tillägg” och ”Kodfragment” i innehållsförteckningen.)

Docs-artiklar använder GFM för de flesta formerna av artikelformatering, som stycken, länkar, listor och rubriker. För en djupare formatering kan artiklar använda Markdig-funktioner som:

- Anteckningsblock
- Inkluderar
- Väljare
- Inbäddade videoklipp
- Kodfragment/-exempel

För en fullständig lista, se ”Markdig- och Markdown-tillägg” och ”Kodfragment” i innehållsförteckningen.

### <a name="note-blocks"></a>Anteckningsblock

Du kan välja bland fyra typer av anteckningsblock för att markera specifikt innehåll:

- OBS
- VARNING
- TIPS
- VIKTIGT

Som regel bör anteckningsblock användas sparsamt eftersom de kan vara störande. Anteckningsblock stöder kodblock, bilder, listor och länkar, men bör vara så enkla som möjligt.

### <a name="includes"></a>Inkluderar

När du har en text- eller bildfil som kan återanvändas och som måste ingå i artikelfiler kan du använda en referens som "inkluderar" filen via funktionen inkludera fil i Markdig. Funktionen ger OPS en instruktion att inkludera den angivna filen i din artikelfil när den byggs, vilket gör den till en del av den publicerade artikeln. Det finns tre typer av inkluderingar som hjälper dig att återanvända innehåll:

- Intern – Återanvänd en vanlig textsträng i en annan mening.
- Block – Återanvänd en hel Markdown-fil som ett block som bäddas in i en del av artikeln.
- Bild – Detta är standardsättet att inkludera bilder i Docs.

Interna inkluderingar och blockinkluderingar är bara enkla Markdown-filer (.md). De kan innehålla alla sorters giltiga Markdowns. Alla inkluderingsfiler i Markdown bör placeras i en [gemensam`/includes` underkatalog](git-github-fundamentals.md#includes-subdirectory) i lagringsplatsens rot. När artikeln publiceras integreras den inkluderade filen sömlöst i den publicerade artikeln.

Här följer krav och överväganden för inkluderingar:

- Använd inkludera när du vill att samma text ska visas i flera artiklar.
- Använd blockinkluderingar för stora mängder innehåll – ett stycke eller två, en delad procedur eller ett delat avsnitt. Använd dem inte för mindre än en mening.
- Inkluderat innehåll återges inte i den renderade vyn för din artikel i GitHub eftersom de använder Markdig-tillägg. De återges först efter publiceringen.
- Kontrollera att all text i en inkludering är skriven i fullständiga meningar eller satser som inte är beroende av föregående eller efterföljande text i artikeln som använder den inkluderade texten. Om du hoppar över detta steg kan en sträng som inte kan översättas skapas, vilket stör den lokaliserade upplevelsen.
- Bädda inte in inkluderingar med andra inkluderingar. De stöds inte.
- Placera mediefiler i en mediemapp som är specifik för inkluderingsunderkatalogen – till exempel, `<repo>`/inkluderingar/mediamapp. Mediekatalogen bör inte innehålla några bilder i sin rot. Om inkluderingen inte har bilder behövs inte en motsvarande mediekatalog.
- Precis som med vanliga artiklar bör du inte dela media mellan inkluderingsfiler. Använd en särskild fil med ett unikt namn för varje inkludering och artikel. Lagra mediefilen i mediemappen som associeras med inkluderingen.
- Använd inte en inkludering som det enda innehållet i en artikel.  Inkluderingar är avsedda att komplettera övrigt innehåll i en artikel.

### <a name="selectors"></a>Väljare

Använd väljare i tekniska artiklar när du skriver olika versioner av samma artikel för att visa implementeringsskillnader för olika tekniker eller plattformar. Detta gäller framför allt för innehåll vår plattform för mobilt innehåll för utvecklare. Det finns för närvarande två typer av väljare i Markdig: en enkel väljare och en multiväljare.

Eftersom samma Markdown för väljare används i alla markerade artiklar rekommenderar vi att du placerar väljaren för en artikel i en inkludering. Du kan sedan hänvisa till den inkluderingen i alla artiklar som använder samma väljare.

### <a name="code-snippets"></a>Kodfragment

Markdig har stöd för avancerad inkludering av kod i artiklar, tack vare kodfragmentstillägget. Tillägget möjliggör avancerad rendering som bygger på GFM-funktioner som programmeringsspråkval och syntaxfärgning, samt användbara funktioner som:

- Inkludering av centraliserade kodexempel/-fragment från externa lagringsplatser.
- Användargränssnitt i flikar för att visa olika versioner av kodexempel i olika språk.

## <a name="gotchas-and-troubleshooting"></a>Information och felsökning

### <a name="alt-text"></a>Alternativ text

Alternativ text som innehåller understreck återges inte korrekt. Till exempel, i stället för att använda detta:

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Använd escape-tecken för understrecken, så här:

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Apostrofer och citattecken

Om du kopierar från Word till en Markdown-redigerare kan texten innehålla ”smarta”(sneda) apostrofer eller citattecken. Dessa måste vara kodade eller ändras till raka apostrofer eller citattecken. Annars kan det se ut så här när filen publiceras: Itâ€™s

Så här skriver du ”smarta” skiljetecken:

- Vänster citattecken: `&#8220;`
- Höger citattecken: `&#8221;`
- Höger, enkelt citattecken eller apostrof: `&#8217;`
- Vänster, enkelt citattecken: `&#8216;`

### <a name="angle-brackets"></a>Vinkelparentes

Om du använder vinkelparenteser i texten (inte koden) – till exempel för att markera en platshållare – måste du skriva hakparenteserna i kod. Annars tror Markdown att det är en HTML-tagg.

Till exempel, koda `<script name>` som `&lt;script name&gt;`

## <a name="see-also"></a>Se även

### <a name="markdown-resources"></a>Markdown-resurser

- [Introduktion till Markdown](https://daringfireball.net/projects/markdown/syntax)
- [Docs Markdown lathund](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [Grunder för Markdown i GitHub](https://help.github.com/articles/markdown-basics/)
