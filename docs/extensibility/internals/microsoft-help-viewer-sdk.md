---
title: "Microsoft 도움말 뷰어 SDK | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 620d7dcd-d462-475e-a449-fbfa06ff12c5
caps.latest.revision: 33
caps.handback.revision: 33
ms.author: "gregvanl"
manager: "ghogen"
---
# Microsoft 도움말 뷰어 SDK
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 문서는 Visual Studio 도움말 뷰어 통합에 대 한 다음과 같은 작업을 포함 되어 있습니다.  
  
-   \(F1 지원\) 항목을 만드는  
  
-   도움말 뷰어에서 콘텐츠 브랜딩 패키지 만들기  
  
-   문서 집합을 배포합니다.  
  
-   Visual Studio shell \(통합 또는 격리\)에 추가 도움말  
  
-   추가 리소스  
  
### \(F1 지원\) 항목을 만드는  
 이 섹션에 표시 된 항목, 항목 요구 사항, 렌더링 된 결과와 항목 \(F1 지원 요구 사항 포함\) 하 고 마지막으로 예제 항목을 만드는 방법에 대 한 간단한 설명의 구성 요소에 대해 간략하게를 제공 합니다.  
  
 **도움말 뷰어 항목 개요**  
  
 항목 렌더링을 위해 호출 되 면 도움말 뷰어 설치 또는 항목 XHTML와 함께 마지막 업데이트 시 주제와 연관 된 브랜딩 패키지 요소를 가져오고 표시할된 콘텐츠 뷰 \(브랜딩 데이터 \+ 항목 데이터\)이 될 두 가지를 결합 합니다.  브랜딩 패키지에 로고, 콘텐츠 동작 및 브랜딩 텍스트 \(저작권 등\)에 대 한 지원이 포함 되어 있습니다.  브랜딩 패키지 요소에 대 한 자세한 내용은 아래의 "브랜딩 패키지 만들기"를 참조 하십시오.  주제와 관련 된 브랜딩 패키지가 없는 인 경우에 도움말 뷰어 \(Branding\_en US.mshc\)의 도움말 뷰어 응용 프로그램 루트에 있는 대체 \(fallback\) 브랜딩 패키지를 사용 합니다.  
  
 **도움말 뷰어 항목 요구 사항**  
  
 제대로 렌더링 도움말 뷰어 내에서 원시 항목 콘텐츠 W3C 기본 1.1 XHTML 이어야 합니다.  
  
 항목에는 일반적으로 두 섹션이 포함 되어 있습니다.  
  
-   메타 데이터 \(메타 데이터 참조 콘텐츠 참조\): 예를 들어 항목의 고유 ID, 키워드 값, 항목 목차 ID를 항목에 대 한 데이터 노드 ID 등의 부모입니다.  
  
-   본문 콘텐츠: W3C 기본 1.1 XHTML 호환 포함 된 콘텐츠 동작 \(축소 가능한 영역, 코드 조각 등 지원 전체 목록은 아래와 같습니다\).  
  
 Visual Studio 브랜딩 패키지 컨트롤을 지원 합니다.  
  
-   링크  
  
-   CodeSnippet  
  
-   CollapsibleArea  
  
-   상속 된 멤버  
  
-   LanguageSpecificText  
  
 지원 되는 언어 문자열 \(하지 대\/소문자 구분\):  
  
-   javascript  
  
-   csharp 또는 c\#  
  
-   cplusplus 또는 visualc \+ \+ 또는 c \+ \+  
  
-   jscript  
  
-   visual basic 또는 vb  
  
-   f \# 또는 fsharp 또는 fs  
  
-   기타 – 언어 이름을 나타내는 문자열  
  
 **도움말 뷰어 항목 만들기**  
  
 라는 ContosoTopic4.htm, XHTML 문서를 새로 만들고 \(아래\)에서는 title 태그를 포함 합니다.  
  
```html  
<html> <head> <title>Contoso Topic 4</title> </head> <body> </body> </html>  
  
```  
  
 다음으로, 방법 항목 \(자체 브랜드 여부\)를 표시 하는 하는 방법을 정의 하는 데이터를 추가 등을 f 1을 목차, 해당 ID \(다른 항목에서 링크 참조\) 내에 있는이 항목에 대 한이 항목을 참조 합니다.  지원 되는 메타 데이터의 전체 목록은 아래 "콘텐츠 메타 데이터" 표를 참조 하십시오.  
  
-   이 경우 고유한 브랜딩 패키지를 Visual Studio 도움말 뷰어 브랜딩 패키지의 변형을 사용 됩니다.  
  
-   F1 메타 이름 및 값 추가 \("Microsoft.Help.F1" 콘텐츠 "ContosoTopic4" \=\)는 IDE 속성 모음에 제공된 된 F1 값 일치 합니다.  \(자세한 내용은 F1 지원 섹션 참조\).   이 F1에 일치 하는 값은 IDE에서 f1 키를 선택 하면이 항목을 표시 하는 IDE 내에서 호출 합니다.  
  
-   항목 ID를 추가 합니다. 이 항목에 연결할 다른 항목에서 사용 되는 문자열입니다.  이 항목에 대 한 도움말 뷰어 ID입니다.  
  
-   목차에 대 한이 항목 TOC 노드 표시 되는 위치를 정의 하려면이 항목의 부모 노드를 추가 합니다.  
  
-   목차,이 항목의 노드 순서를 추가 합니다. 부모 노드 n 개의 자식 노드가 있으면 자식 노드 순서 대로이 항목의이 위치를 정의 합니다. 예를 들어이 항목은 4 개의 자식 항목의 4 번입니다.\)  
  
 예제에서는 메타 데이터 섹션:  
  
```html  
<html> <head> <title>Contoso Topic 4</title> <meta name="SelfBranded" content="false" /> <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" /> <meta name="Microsoft.Help.Id" content="ContosoTopic4" /> <meta name="Microsoft.Help.F1" content=" ContosoTopic4" /> <meta name="Language" content="en-us" /> <meta name="Microsoft.Help.TocParent" content="ContosoTopic0" /> <meta name="Microsoft.Help.TocOrder" content="4" /> </head> <body> </body> </html>  
  
```  
  
 **항목 본문**  
  
 항목의 본문 \(머리글 및 바닥글 제외 함\)는 페이지 링크, 참고 섹션, 축소 가능한 영역, 코드 조각 및 특정 텍스트 언어의 섹션에 포함 됩니다.  표시 된 항목의 해당 영역에 대 한 정보에 대 한 브랜딩 섹션을 참조 합니다.  
  
1.  항목 title 태그를 추가 합니다.  `<div class="title">Contoso Topic 4</div>`  
  
2.  참고 섹션을 추가 합니다. `<div class="alert"> add your table tag and text </div>`  
  
3.  축소 가능한 영역을 추가 합니다.  `<CollapsibleArea Expanded="1" Title="Collapsible Area Test Heading"> add text  </CollapsibleArea>`  
  
4.  코드 조각을 추가 합니다.  `<CodeSnippet EnableCopyCode="true" Language="CSharp" ContainsMarkup="false" DisplayLanguage="C#" > a block of code </CodeSnippet>`  
  
5.  추가 코드 언어에 대 한 특정 텍스트:  `<LanguageSpecificText devLangcs="CS" devLangvb="VB" devLangcpp="C++" devLangnu="F#" />` 해당 devLangnu 참고 \= 다른 언어를 입력할 수 있습니다. 예를 들어 devLangnu \= "Fortran" Fortran 표시 됩니다 때 코드 조각을 DisplayLanguage Fortran \=  
  
6.  페이지 링크를 추가 합니다. `<a href="ms-xhelp://?Id=ContosoTopic1">Main Topic</a>`  
  
> [!NOTE]
>  참고: 지원 되지 않는 새로운 "표시 언어" \(예: F \#, Cobol, Fortran\)에 대 한 코드 조각에서 코드 색 조정이 됩니다 단색 합니다.  
  
 **예제 도움말 뷰어 항목** 코드에는 메타 데이터, 코드 조각, 축소 가능한 영역 및 특정 텍스트 언어를 정의 하는 방법을 보여 줍니다.  
  
```  
<?xml version="1.0" encoding="utf-8"?> <html> <head> <title>Contoso Topic 4</title> <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" /> <meta name="Microsoft.Help.Id" content="ContosoTopic4" /> <meta name="Microsoft.Help.F1" content=" ContosoTopic4" /> <meta name="Language" content="en-us" /> <meta name="Microsoft.Help.TocParent" content="ContosoTopic0" /> <meta name="Microsoft.Help.TocOrder" content="4" /> <meta name="SelfBranded" content="false" /> </head> <body> <div class="title">Contoso Topic 4</div> <div id="header"> <table id="bottomTable" cellpadding="0" cellspacing="0"  width="100%"> <tr id="headerTableRow2"><td align="left"> <span id="nsrTitle">Contoso Topic 1</span> </td> <td align="right"> </td></tr> <tr id="headerTableRow1"><td align="left"> <span id="runningHeaderText">Contoso Widgets & Sprockets</span> </td></tr> </table> </div> <h2>Table of Contents</h2> <ul class="toc"> <li class="tocline1"><a href="#introduction" target="_self">1.0 Introduction</a></li> <li class="tocline1"><a href="#seealso" target="_self">2.1 See Also</a></li> </ul> <div class="topic"> <div id="mainSection"> <div id="mainBody"> <a name="introduction"></a> <h2>1.0 Introduction</h2> <p>[This documentation is for sample purposes only.]</p> <p>Contoso Topic 1 contains examples of: <ul> <li>Collapsible Area</li> <li>Bookmark ("See also")</li> <li>Code Snippets from Branding Package</li> </ul> </p> <div class="alert"><table><tr><th> <strong>Note </strong></th></tr> <tr><td> <p>This is an example of a <span class="label">Note </span>section. Call out important items for your reader in this <span class="label">Note </span>box. </p></td></tr> </table> </div> </div> <CollapsibleArea Expanded="1" Title="Collapsible Area Test Heading"> <a id="sectionToggle0"><!----></a> <div> Example of Collapsible Area <br/> Lorem ipsum dolor sit amet... </div> </CollapsibleArea> <div id="snippetGroup" > <CodeSnippet EnableCopyCode="true" Language="VisualBasic" ContainsMarkup="false" DisplayLanguage="Visual Basic" > Private Sub ToolStripRenderer1_RenderGrip(sender as Object, e as ToolStripGripRenderEventArgs) _ Handles ToolStripRenderer1.RenderGrip Dim messageBoxVB as New System.Text.StringBuilder() messageBoxVB.AppendFormat("{0} = {1}", "GripBounds", e.GripBounds) messageBoxVB.AppendLine() ... MessageBox.Show(messageBoxVB.ToString(),"RenderGrip Event") End Sub </CodeSnippet> <CodeSnippet EnableCopyCode="true" Language="CSharp" ContainsMarkup="false" DisplayLanguage="C#" > private void ToolStripRenderer1_RenderGrip(Object sender, ToolStripGripRenderEventArgs e) { System.Text.StringBuilder messageBoxCS = new System.Text.StringBuilder(); messageBoxCS.AppendFormat("{0} = {1}", "GripBounds", e.GripBounds ); messageBoxCS.AppendLine(); ... MessageBox.Show(messageBoxCS.ToString(), "RenderGrip Event" ); } </CodeSnippet> <CodeSnippet EnableCopyCode="true" Language="fsharp" ContainsMarkup="false" DisplayLanguage="F#" > some F# code </CodeSnippet> </div> <h4 class="subHeading">Example of code specific text</h4>Language = <LanguageSpecificText devLangcs="CS" devLangvb="VB" devLangcpp="C++" devLangnu="F#" /> <a name="seealso"></a> <h1 class="heading">See Also</h1> <div id="seeAlsoSection" class="section"> <div class="seeAlsoStyle"> <a href="ms-xhelp://?Id=ContosoTopic1">Main Topic</a> </div> </div> </div> </div> </body> </html>  
  
```  
  
 **F1 키 지원**  
  
 Visual Studio에서 f1 키를 선택 하면 IDE 내에서 커서의 위치에서 제공 하는 값을 생성을 채우는 "속성 모음"는 제공 된 값 \(커서 위치에 기반 합니다. 커서가 기능 x 위에 있는 x 기능이 액티브\/포커스 이며 값을 가진 속성 모음을 채웁니다.  F 1을 선택 하는 속성 모음 채워집니다 및 Visual Studio F1 코드가 고객 기본 도움말 소스 로컬 또는 온라인 인지 \(온라인 기본값임\), 다음을 설정 하는 사용자 수에 따라 적절 한 문자열을 만듭니다 \(온라인 기본값임\) – 셸 실행 \(도움말 관리자 가이드 exe에 대 한 시작 매개 변수가 참조\)에서 로컬 도움말 뷰어 \+ 로컬 도움말 기본값이 면 propertybag에서 키워드에 대 한 매개 변수를 사용 또는 MSDN URL 매개 변수 목록에 키워드를 사용 합니다.  
  
 다중값 문자열로 수행할 첫 번째 단어 봐를 적중에 대 한 세 개의 문자열에 대 한 F1 반환 되는 경우 참조 하는 경우 발견 완료 되 고, 및 그렇지 않으면 다음 문자열을 이동 합니다.  순서가 중요합니다. 다중 값 키워드의 표시에는 가장 짧은 문자열에 가장 긴 문자열 이어야 합니다.  이 다중값 키워드에 대 한 경우 확인 하려면 선택한 키워드를 포함 하는 온라인 F1 URL 문자열을 살펴봅니다.  
  
 Visual Studio 2012에서 우리 일부러 더 강력한 나누기 온라인 및 오프 라인 사이 온라인에 대 한 사용자의 설정 되었으면 다음 우리 단순히 F1 요청에 직접 전달 온라인 쿼리 서비스 Visual Studio 2010에서 사용 했던 도움말 라이브러리 에이전트를 통해 보다는 MSDN에 있습니다. 다음의 상태에 의존 "설치 된 공급 업체 콘텐츠 \= true" 해당 컨텍스트에서 다른 작업을 수행할 것인지 결정 합니다. True 인 경우, 그런 후 고객에 대 한 지원 하려는 따라이 구문 분석 및 라우팅 논리를 수행 합니다. False 인 경우, 다음 방금로 MSDN 합니다. 사용자의 설정이 로컬 이면 다음 모든 호출은 이동 하면 로컬 도움말 엔진에 됩니다.  
  
 F1 흐름 다이어그램:  
  
 ![F1 flow](../../extensibility/internals/media/f1flow.png "F1flow")  
  
 온라인 \(브라우저에서 실행\)로 도움말 뷰어 기본 도움말 콘텐츠 소스를 설정 된 경우:  
  
-   Visual Studio 파트너 \(VSP\) 기능을 F1 속성 모음 \(속성 모음 prefix.keyword 및 레지스트리에서 찾을 접두사에 대 한 온라인 URL\) 값을 내보낼: F1 VSP URL \+ 매개 변수를 브라우저에 보냅니다.  
  
-   Visual Studio 기능 \(언어 편집기, Visual Studio 특정 메뉴 항목 등\): F1 Visual Studio URL을 브라우저에 보냅니다.  
  
 로컬 도움말 \(도움말 뷰어에서 실행\)로 도움말 뷰어 기본 도움말 콘텐츠 소스를 설정 된 경우:  
  
-   VSP 기능 키워드 F1 속성 모음 및 로컬 저장소 인덱스 간에 일치 하는 위치 \(속성 모음 prefix.keyword 즉, 로컬 저장소 인덱스에 있는 값 \=\): F1 도움말 뷰어에서 항목을 렌더링 합니다.  
  
-   Visual Studio 기능 \(Visual Studio 기능에서 내보낸 속성 모음을 재정의 하려면 VSP에 대 한 옵션 없음\): F1 도움말 뷰어에서 Visual Studio 항목을 렌더링 합니다.  
  
 공급 업체 도움말 콘텐츠에 대 한 F1 대체 \(fallback\)를 사용 하도록 설정 하려면 다음 레지스트리 값을 설정 합니다. F1 대체 \(fallback\)는 도움말 뷰어 F1 도움말 콘텐츠를 찾고 온라인으로 설정 하 고 공급 업체 콘텐츠를 사용자의 하드 드라이브에 로컬로 설치를 의미 합니다. 도움말 뷰어는 경우에 기본 설정에 대 한 온라인 도움말 콘텐츠에 대 한 로컬 도움말에 표시 됩니다.  
  
1.  설정의 **VendorContent** 2.1 도움말 레지스트리 키 아래의 값:  
  
    -   32 비트 운영 체제:  
  
         HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Help\\v2.1\\Catalogs\\VisualStudio12  
  
         "VendorContent" \= dword: 00000001  
  
    -   64 비트 운영 체제:  
  
         HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Help\\v2.1\\Catalogs\\VisualStudio12  
  
         "VendorContent" \= dword: 00000001  
  
2.  2.1 도움말 레지스트리 키에서 파트너 네임 스페이스를 등록 합니다.  
  
    -   32 비트 운영 체제:  
  
         HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Help\\v2.1\\Partner*\\ \< 네임 스페이스 \>*  
  
         "위치" \= "오프 라인"  
  
    -   64 비트 운영 체제:  
  
         HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Help\\v2.1\\Partner*\\ \< 네임 스페이스 \>*  
  
         "위치" \= "오프 라인"  
  
 **구문 분석 하는 기본 기본 네임 스페이스**  
  
 기본 네임 스페이스를 기본 구문 분석을 설정 하려면 레지스트리에 추가 새 DWORD 이름: BaseNativeNamespaces 및 값 1 \(아래 지원 하고자 하는 카탈로그 키\)로 설정 합니다.  예를 들어 Visual Studio 카탈로그를 사용 하려는 경우 키의 경로를 추가할 수 있습니다.  
  
 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Help\\v2.1\\Catalogs\\VisualStudio12  
  
 경우 헤더\/메서드 발견 되는 형식에는 F1 키워드 '\/' 문자 구문 분석 됩니다 out, 다음 구문에 발생 합니다.  
  
-   헤더: 레지스트리에 등록에 사용할 수 있는 네임 스페이스가 됩니다 합니다.  
  
-   방법: 키워드를 통해 전달 되는이 됩니다.  
  
 예를 들어 CustomLibrary 라는 사용자 지정 라이브러리 및 요청에 제공 하는 F1는 형식으로 지정 하는 경우, MyTestMethod 라는 메서드가 `CustomLibrary/MyTestMethod`합니다.  
  
 사용자 다음 파트너 하이브 아래 네임 스페이스와 CustomLibrary를 등록 하 고 원하는 어떤 위치 키를 제공 하 고 쿼리에 전달 되는 키워드는 MyTestMethod입니다.  
  
 **디버깅 도구는 IDE에서 도움말을 사용 하도록 설정**  
  
 다음 레지스트리 키와 값을 추가 합니다.  
  
 HKEY\_CURRENT\_USER\\Software\\Microsoft\\VisualStudio\\12.0\\Dynamic 도움말 키: 소매 가격에서 디버그 출력 표시: 예  
  
 Ide에서 도움말 메뉴 항목에서 "도움말 컨텍스트 디버그"를 선택 합니다.  
  
 **콘텐츠 메타 데이터**  
  
 다음 표에서 대괄호 사이 나타나는 모든 문자열에는 올바른된 값으로 바꿔야 하는 자리 표시자입니다. 예를 들어 \< 메타 name\="Microsoft.Help.Locale" 콘텐츠 \= "\[언어 코드\]" \/ \>, 예: "\[언어 코드\]"는 값으로 대체 해야 합니다 "en\-us"입니다.  
  
|속성 \(HTML 표시\)|설명|  
|--------------------|--------|  
|\< 메타 name\="Microsoft.Help.Locale" 콘텐츠 \= "\[코드 언어\]" \/ \>|이 항목에 대 한 로캘을 설정합니다. 항목에서이 태그를 사용 하는 경우 한 번만 사용 해야 하 고 다른 Microsoft 도움말 태그 위에 삽입 해야 합니다. 이 항목의 본문 텍스트; 지정 된 경우에 제품 로캘과 연관 된 단어 분리기를 사용 하 여 인덱싱됨이 태그를 사용 하지 않는 경우 그렇지 않은 경우는 en\-우리 단어 분리기를 사용 합니다. 이 태그는 ISOC RFC 4646을 준수합니다. Microsoft 도움말 올바르게 작동을 보장 하려면 일반 언어 특성 대신이 속성을 사용 합니다.|  
|\< 메타 name\="Microsoft.Help.TopicLocale" 콘텐츠 \= "\[코드 언어\]" \/ \>|다른 로캘에서도 사용 하는 경우이 항목에 대 한 로캘을 설정 합니다. 항목에서이 태그를 사용 하는 경우 한 번만 사용 되어야 합니다. 카탈로그에 둘 이상의 언어로 콘텐츠를에서 포함 하는 경우에이 태그를 사용 합니다. 카탈로그에 여러 항목 같은 ID를 수 있지만 각 고유 TopicLocale 지정 해야 합니다. 카탈로그의 로캘과 일치 하는 TopicLocale를 지정 하는 항목은의 목차에 표시 되는 항목입니다. 그러나이 항목의 모든 언어 버전은 검색 결과에 표시 됩니다.|  
|\< 제목 \> \[제목\] \< \/ t \>|이 항목의 제목을 지정합니다. 이 태그 필수적 요소 이며, 항목을 한 번만 사용 해야 합니다. 이 항목의 본문에 제목 \< div \> 섹션을 찾을 수 없는 경우이 제목은 목차와 항목에 표시 됩니다.|  
|\< 메타 이름 \= "Microsoft.Help.Keywords" 콘텐츠 \= "\[aKeywordPhrase\]" \/ \>|도움말 뷰어의 인덱스 창에 표시 되는 링크의 텍스트를 지정 합니다. 링크를 클릭 하는 경우에 항목이 표시 됩니다. 항목에 대 한 여러 인덱스 키워드를 지정할 수 또는 인덱스에 표시 하려면이 항목에 대 한 링크를 원하지 않는 경우이 태그를 생략할 수 있습니다. 이 속성에 이전 버전의 도움말에서 "K" 키워드를 변환할 수 있습니다.|  
|\< 메타 name\="Microsoft.Help.Id" 콘텐츠 \= "\[TopicID\]" \/ \>|이 항목에 대 한 식별자를 설정합니다. 이 태그 필수적 요소 이며, 항목을 한 번만 사용 해야 합니다. ID가 같은 로캘 설정을 하는 카탈로그의 항목 간에 고유 해야 합니다. 다른 항목에서이 ID를 사용 하 여이 항목에 대 한 링크를 만들 수 있습니다.|  
|\< 메타 name\="Microsoft.Help.F1" content\="\[System.Windows.Controls.Primitives.IRecyclingItemContainerGenerator\]"\/ \>|이 항목에 대 한 F1 키워드를 지정합니다. 항목에 대 한 여러 F1 키워드를 지정할 수 또는이 항목을 응용 프로그램 사용자가 f1 키를 누를 때 표시할 하지 않으려는 경우이 태그를 생략할 수 있습니다. 일반적으로 항목에 대 한 F1 키워드를 하나만 지정 됩니다. 이 속성에 이전 버전의 도움말에서 "F" 키워드를 변환할 수 있습니다.|  
|\< 메타 이름 \= "설명" content \= "\[항목 설명\]" \/ \>|이 항목의 내용에 대 한 간단한 요약을 제공합니다. 항목에서이 태그를 사용 하는 경우 한 번만 사용 되어야 합니다. 이 속성은 쿼리 library;에서 직접 액세스 인덱스 파일에 저장 되지 않습니다.|  
|\< 메타 name\="Microsoft.Help.TocParent" 콘텐츠 \= "\[parent\_Id\]" \/ \>|목차에서이 항목의 부모 항목을 지정합니다. 이 태그 필수적 요소 이며, 항목을 한 번만 사용 해야 합니다. 값은 부모의 Microsoft.Help.Id. 항목의 내용에 대 한 테이블의 한 위치를 가질 수 있습니다. "\-1"에 목차 루트에 대 한 항목 ID로 간주 됩니다.[!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)], 해당 페이지에는 도움말 뷰어 홈 페이지입니다. 특히 TocParent \= 1 표시 되는 것 맨 위에 있는 수준 수 있도록 몇 가지 항목을 추가 하는 동일한 이유입니다. 도움말 뷰어 홈 페이지는 시스템 페이지와 하므로 대체 불가능 합니다. VSP을\-1의 ID로 페이지를 추가 하려고 하는 경우 콘텐츠 집합에 추가 얻을 수 있습니다 있지만 도움말 뷰어는 도움말 뷰어 홈 시스템 페이지\-항상 사용|  
|\< 메타 name\="Microsoft.Help.TocOrder" 콘텐츠 \= "\[양의 정수\]" \/ \>|여기서는 목차에서이 항목은 해당 피어 항목을 기준으로 지정 합니다. 이 태그 필수적 요소 이며, 항목을 한 번만 사용 해야 합니다. 값은 정수입니다. 값이 더 낮은 정수를 지정 하는 항목 값이 더 높은 정수를 지정 하는 항목 위에 나타납니다.|  
|\< 메타 name\="Microsoft.Help.Product" 콘텐츠 \= "\[product code\]" \/ \>|이 항목에서 설명 하는 제품을 지정 합니다. 항목에서이 태그를 사용 하는 경우 한 번만 사용 되어야 합니다. 이 정보는 도움말 인덱서에 전달 되는 매개 변수로 제공할 수도 있습니다.|  
|\< 메타 name\="Microsoft.Help.ProductVersion" 콘텐츠 \= "\[version number\]" \/ \>|이 항목에 설명 된 제품의 버전을 지정 합니다. 항목에서이 태그를 사용 하는 경우 한 번만 사용 되어야 합니다. 이 정보는 도움말 인덱서에 전달 되는 매개 변수로 제공할 수도 있습니다.|  
|\< 메타 name\="Microsoft.Help.Category" 콘텐츠 \= "\[문자열\]" \/ \>|제품 사용 콘텐츠의 하위 섹션을 식별 합니다. 항목에 대 한 여러 하위 섹션을 식별할 수 또는 모든 하위 섹션을 식별 하는 링크를 원하지 않는 경우이 태그를 생략할 수 있습니다. 이 태그는 특성을 저장 TargetOS 및 TargetFrameworkMoniker에 대 한 도움말의 이전 버전에서 항목을 변환할 때 사용 됩니다. 콘텐츠 형식은 AttributeName:AttributeValue입니다.|  
|\< 메타 name\="Microsoft.Help.TopicVersion 내용 \="\[항목 버전 번호\]"\/ \>|카탈로그에 여러 버전이 있을 경우이 버전의 항목을 지정 합니다. Microsoft.Help.Id은 고유 하 게 아닙니다 때문에 항목의 둘 이상의 버전이 카탈로그에는.NET Framework 4에 대 한.NET Framework 3.5 및 항목에 대 한 항목을 포함 하 고 모두 동일한 Microsoft.Help.Id 예를 들어 카탈로그에 있는 경우이 태그가 필요 합니다.|  
|\< 메타 이름 \= "SelfBranded" content \= "\[TRUE 또는 FALSE\]" \/ \>|이 항목에서 도움말 라이브러리 관리자 시작 브랜딩 패키지 또는 항목에만 적용 되는 브랜딩 패키지를 사용 하는지 여부를 지정 합니다. 이 태그는 TRUE 여야 합니다. 또는 FALSE입니다. 있으면 TRUE, 관련된 항목에 대 한 브랜딩 패키지는 다른 콘텐츠의 렌더링에서 서로 다른 경우에 의도 한 대로 항목 렌더링 되도록 도움말 라이브러리 관리자를 시작할 때 설정 된 브랜딩 패키지를 재정의 하 여 합니다. FALSE 인 경우 현재 항목은 도움말 라이브러리 관리자를 시작할 때 설정 된 브랜딩 패키지에 따라 렌더링 됩니다. 기본적으로 도움말 라이브러리 관리자 가정 SelfBranded 변수가 TRUE;로 선언 된 경우가 아니면 false로 자체 브랜딩 선언할 필요가 없습니다 따라서 \< 메타 이름 \= "SelfBranded" content \= "FALSE" \/ \>입니다.|  
  
### 브랜딩 패키지 만들기  
 Visual Studio 릴리스는 Visual Studio 파트너에 대 한 격리 및 통합된 셸을 비롯 한 다양 한 Visual Studio 제품의 수를 포함 합니다.  이러한 제품의 각 항목 기반으로 도움말 콘텐츠의 지원, 제품에 고유한 브랜딩 어느 정도 필요 합니다.  예를 들어 Visual Studio 항목 자체 고유 도움말 내용에 대 한 브랜딩 각 항목을 ISO 셸을 래핑하면 SQL Studio를 사용 해야 하지만 일관 된 브랜드 프레젠테이션에가 필요 합니다.  통합 셸을 파트너의 도움말 항목 브랜딩 자신의 항목을 유지 하면서 부모 Visual Studio 제품 도움말 콘텐츠 내에 좋습니다.  
  
 브랜딩 패키지는 도움말 뷰어를 포함 하는 제품으로 설치 됩니다.  Visual Studio 제품:  
  
-   대체 \(fallback\) 브랜딩 패키지 \(Branding\_ \< 로캘 \>.mshc\) 도움말 뷰어 2.1 응용 프로그램 루트에 설치 됩니다 \(예: C:\\Program Files \(x86\) \\Microsoft Help Viewer\\v2.1\) 도움말 뷰어 언어 팩으로 합니다.  이 패키지를 브랜딩 제품 되지 설치 되어 없는 경우에 사용 됩니다 \(콘텐츠 없음 설치가 완료 된 후\) 설치 된 브랜딩 패키지 없거나 손상 되었습니다.  Note 패키지를 브랜딩 하는 응용 프로그램 루트 대체 사용 되는 경우 Visual Studio 요소 \(로고 및 피드백\)는 무시 됩니다.  
  
-   Visual Studio 콘텐츠를 콘텐츠 패키지 서비스에서 설치 \(첫 번째 시간 콘텐츠 설치 시나리오\)에 대 한 브랜딩 패키지도 설치 됩니다.  없을 경우 브랜딩 패키지에 대 한 업데이트, 추가 패키지 설치 작업 또는 다음 콘텐츠 업데이트 발생할 때 업데이트가 설치 됩니다.  
  
 Microsoft 도움말 뷰어 항목 메타 데이터에 따라 항목의 브랜딩 지원 합니다.  
  
-   항목 메타 데이터 정의 자체 브랜드 \= true, 렌더링 되는 항목, 브랜딩\) \(보면 아무 작업도 수행 합니다.  
  
-   항목 메타 데이터 정의 자체 브랜드 \= false, TopicVendor 메타 데이터 값과 관련 된 브랜딩 패키지를 사용 합니다.  
  
-   여기서 항목 메타 데이터 정의 name\="Microsoft.Help.TopicVendor" 콘텐츠 \= \< 브랜딩 패키지 이름 MSHA 공급 업체에 \>, 콘텐츠 값에 정의 된 브랜딩 패키지를 사용 합니다.  
  
-   Visual Studio 카탈로그 내에서 브랜딩 패키지의 우선 순위 응용 프로그램이 참고 합니다.  첫 번째 Visual Studio 기본 브랜딩 적용 되 고 그런 다음 항목 메타 데이터에 정의 된 지원 \(설치 msha에 정의 됨\) 하는 대로 패키지를 연결 된 브랜딩, 브랜딩 공급 업체 정의 된 재정의로 적용 됩니다.  
  
 브랜딩 요소는 일반적으로 세 가지 주요 범주로 구분 됩니다.  
  
-   헤더 요소 \(예를 들면 사용자 의견 링크, 조건부 고 지 사항 텍스트, 로고\)  
  
-   동작 \(예제는 확장\/축소 컨트롤 텍스트 요소를 포함 하 고 코드 조각 요소\) 콘텐츠  
  
-   바닥글 요소 \(예: 저작권 정보\)  
  
 : 브랜드가 지정 된 요소가 포함 된 것으로 간주 하는 항목 \(이 사양에 자세히 설명\):  
  
-   카탈로그\/제품 로고 \(예:, Visual Studio\)  
  
-   사용자 의견 링크 및 전자 메일 요소  
  
-   고 지 사항 텍스트  
  
-   저작권 텍스트  
  
 관련 파일을 Visual Studio 도움말 뷰어 브랜딩 패키지에는 다음과 같습니다.  
  
-   그래픽 \(로고, 아이콘 등\)  
  
-   Branding.js – 스크립트 파일 지원 콘텐츠 동작  
  
-   Branding.xml 카탈로그 내용 간의 일관 되 게 사용 되는 문자열입니다.  참고: Visual Studio는 branding.xml 지역화 텍스트 요소 포함 \_locID \= "\< 고유 값 \>"  
  
-   Branding.css – 프레젠테이션 일관성에 대 한 스타일 정의  
  
-   Printing.css\-인쇄 된 일관성 있는 프레젠테이션에 대 한 스타일 정의  
  
 위에서 언급 했 듯이 브랜딩 패키지 항목와 관련이 있습니다.  
  
-   때 SelfBranded \= false 메타 데이터에 정의 되 면 패키지를 브랜딩 하는 카탈로그를 상속 하는 항목  
  
-   또는 SelfBranded \= false를 반환 하며 고유한 브랜딩 패키지 및에 정의 되어 MSHA는 사용할 수 있는 콘텐츠를 설치 하는 경우  
  
 브랜딩 사용자 지정 패키지를 구현 하는 Vsp에 대 한 \(VSP 콘텐츠, SelfBranded \= True\), \(도움말 뷰어 설치 됨\) 대체 \(fallback\) 브랜딩 패키지 시작 하 고 적절 하 게 파일의 이름을 변경 하는 하나의 방법입니다.  \< 로캘 \> Branding\_.mshc 파일이.mshc로 변경 하는 파일 확장명을 가진 zip 파일이 하면.mshc에서 확장명을.zip으로 변경 하 고 압축을 풉니다.  아래 브랜딩 패키지 요소에 대 한 보고 수정할 적절 하 게 \(예를 들어 VSP 로고와 Branding.xml 파일의 로고에 대 한 참조를 로고 변경, VSP에 대 한 구체적인 등 당 Branding.xml 업데이트\) 합니다.  
  
 모든 수정 작업을 완료 하는 경우 원하는 브랜딩 요소를 포함 하는 zip 파일을 만들고.mshc로 확장명을 변경 합니다.  
  
 브랜딩 사용자 지정 패키지를 연결 하려면 \(항목 포함\) 콘텐츠 mshc 함께 브랜딩 mshc 파일에 대 한 참조를 포함 하는 MSHA를 만듭니다.  기본 MSHA를 만드는 방법에 대 한 "MSHA" 아래를 참조 하십시오.  
  
 항목을 포함 하는 경우 항목의 특정 항목을 일관 되 게 렌더링 하는 데 사용 되는 목록 요소를 포함 하는 Branding.xml 파일 \< 메타 name\="Microsoft.Help.SelfBranded" 콘텐츠 \= "false" \/ \>입니다.  Visual Studio에 대 한 목록이 Branding.xml 파일의 요소에에서는 다음과 같습니다.  Note이 목록은 자신의 제품 브랜딩 요구에 맞게 이러한 요소 \(예: 로고, 피드백 및 저작권 정보\)를 수정할 수 있는 ISO 셸 사용자에 대 한 템플릿으로 사용 될 하도록 되어 있습니다.  
  
 참고: "{n}"에 감지 된 변수 코드 종속성이 있는 – 제거 하거나 이러한 값을 변경 하면 오류 및 응용 프로그램이 충돌 합니다. 지역화 식별자 \(예에서는 \_locID\="codesnippet.n"\)는 Visual Studio 브랜딩 패키지에 포함 됩니다.  
  
 **Branding.xml**  
  
|||  
|-|-|  
|기능:|**CollapsibleArea**|  
|사용:|텍스트 축소 콘텐츠 컨트롤을 확장 합니다.|  
|**요소**|**값**|  
|ExpandText|확장|  
|CollapseText|축소|  
|기능:|**CodeSnippet**|  
|사용:|코드 조각 컨트롤 텍스트입니다.  참고: 코드 조각 내용 "아님" 공간이 공간으로 변경 됩니다.|  
|**요소**|**값**|  
|CopyToClipboard|클립보드에 복사|  
|ViewColorizedText|채색 된 텍스트 보기|  
|CombinedVBTabDisplayLanguage|Visual Basic \(샘플\)|  
|VBDeclaration|선언|  
|VBUsage|사용량|  
|기능:|**피드백, 바닥글 및 로고**|  
|사용:|전자 메일을 통해 현재 항목에 대 한 피드백을 제공 하는 고객에 대 한 피드백 컨트롤을 제공 합니다.  콘텐츠에 대 한 저작권 텍스트입니다.  로고의 정의입니다.|  
|**요소**|**값 \(콘텐츠 최초 사용자 요구에 맞게 이러한 문자열을 수정할 수 있습니다.\)**|  
|저작권 정보|© 2013 Microsoft Corporation입니다. All rights reserved.|  
|SendFeedback|\<는 href \= "{0}"이 \(가\) \\{1\\} \> 사용자 의견 보내기 \<\/a \> Microsoft에이 주제에 있습니다.|  
|FeedbackLink||  
|LogoTitle|[!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)]|  
|LogoFileName|vs\_logo\_bk.gif|  
|LogoFileNameHC|vs\_logo\_wh.gif|  
|기능:|**고지 사항**|  
|사용:|컴퓨터에 대 한 특정 한계 사례 집합 콘텐츠를 변환합니다.|  
|**요소**|**값**|  
|MT\_Editable|이 문서에는 기계 번역 되었습니다. 인터넷에 연결 하는 경우이 페이지를 보려면 원본 영어 콘텐츠를 사용 하 여 편집 가능한 모드에 동시에 "온라인에서이 항목 보기"를 선택 합니다.|  
|MT\_NonEditable|이 문서에는 기계 번역 되었습니다. 인터넷에 연결 하는 경우이 페이지를 보려면 원본 영어 콘텐츠를 사용 하 여 편집 가능한 모드에 동시에 "온라인에서이 항목 보기"를 선택 합니다.|  
|MT\_QualityEditable|이 문서를 수동으로 번역 되었습니다. 인터넷에 연결 하는 경우이 페이지를 보려면 원본 영어 콘텐츠를 사용 하 여 편집 가능한 모드에 동시에 "온라인에서이 항목 보기"를 선택 합니다.|  
|MT\_QualityNonEditable|이 문서를 수동으로 번역 되었습니다. 인터넷에 연결 하는 경우이 페이지를 보려면 원본 영어 콘텐츠를 사용 하 여 편집 가능한 모드에 동시에 "온라인에서이 항목 보기"를 선택 합니다.|  
|MT\_BetaContents|이 문서는 예비 릴리스를 위해 번역 하는 컴퓨터입니다. 인터넷에 연결 하는 경우이 페이지를 보려면 원본 영어 콘텐츠를 사용 하 여 편집 가능한 모드에 동시에 "온라인에서이 항목 보기"를 선택 합니다.|  
|MT\_BetaRecycledContents|이 문서는 사전 릴리스를 위해 수동으로 번역 되었습니다. 인터넷에 연결 하는 경우이 페이지를 보려면 원본 영어 콘텐츠를 사용 하 여 편집 가능한 모드에 동시에 "온라인에서이 항목 보기"를 선택 합니다.|  
|기능:|**LinkTable**|  
|사용:|온라인 항목 링크에 대 한 지원|  
|**요소**|**값**|  
|LinkTableTitle|연결 테이블|  
|TopicEnuLinkText|컴퓨터에서 사용할 수 있는이 항목의 영어 버전 \<\/a \>을 봅니다.|  
|TopicOnlineLinkText|이 항목을 보려면 \<는 href \= "{0}"이 \(가\) \\{1\\} \> 온라인 \<\/a \>|  
|OnlineText|온라인|  
|기능:|**비디오 오디오 컨트롤**|  
|사용:|요소 및 비디오 콘텐츠에 대 한 텍스트를 표시 합니다.|  
|**요소**|**값**|  
|MultiMediaNotSupported|{0} 콘텐츠를 지원 하도록 Internet Explorer 9 이상이 설치 되어야 합니다.|  
|VideoText|비디오를 표시합니다.|  
|AudioText|스트리밍 오디오|  
|OnlineVideoLinkText|\< p \>이 항목과 연계 된 비디오를 보려면 {0}를 클릭 \<는 href \= "\\\\ {1 \\\\}" \> \\{2\\}here \<\/a \>. \<\/p \>|  
|OnlineAudioLinkText|\< p \>이 항목과 관련 된 오디오 듣기에 {0}를 클릭 \<는 href \= "\\\\ {1 \\\\}" \> \\{2\\}here \<\/a \>. \<\/p \>|  
|기능:|**설치 되지 않은 콘텐츠 컨트롤**|  
|사용:|Contentnotinstalled.htm의 렌더링에 사용 되는 텍스트 요소 \(문자열\)|  
|**요소**|**값**|  
|ContentNotInstalledTitle|콘텐츠는 컴퓨터에서 발견 되었습니다.|  
|ContentNotInstalledDownloadContentText|사용자의 컴퓨터에 콘텐츠를 다운로드 하려면 \< p \> \<는 href \= "{0}"이 \(가\) \\{1\\} \> \<\/a \> 관리 탭을 클릭 합니다. \<\/p \>|  
|ContentNotInstalledText|\< p \> 아니요 콘텐츠는 컴퓨터에 설치 됩니다. 로컬 도움말 콘텐츠 설치 합니다. \<\/p \>에 대 한 관리자를 참조 하십시오|  
|기능:|**항목 컨트롤 찾을 수 없습니다.**|  
|사용:|Topicnotfound.htm의 렌더링에 사용 되는 텍스트 요소 \(문자열\)|  
|**요소**|**값**|  
|TopicNotFoundTitle|컴퓨터에 요청 된 항목을 찾을 수 없습니다.|  
|TopicNotFoundViewOnlineText|\< p \> 요청한 주제가 사용자 컴퓨터에 없습니다. 하지만 할 수 있습니다 \<는 href \= "{0}"이 \(가\) \\{1\\} \> 보기의 항목 온라인 \<\/a \>. \<\/p \>|  
|TopicNotFoundDownloadContentText|\< p \> 탐색 창을 유사한 항목에 대 한 링크를 참조 하십시오. 또는 \<는 href \= "{0}"이 \(가\) \\{1\\} \> 콘텐츠를 다운로드 하 여 컴퓨터. \<\/p \> \<\/a \> 관리 탭을 클릭 합니다.|  
|TopicNotFoundText|\< p \> 요청한 주제가 찾을 수 없습니다. \<\/p \>|  
|기능:|**항목 컨트롤 손상**|  
|사용:|Topiccorrupted.htm의 렌더링에 사용 되는 텍스트 요소 \(문자열\)|  
|**요소**|**값**|  
|TopicCorruptedTitle|요청된 된 항목을 표시할 수 없습니다.|  
|TopicCorruptedViewOnlineText|\< p \> 도움말 뷰어는 요청된 된 항목을 표시할 수 없습니다. 항목의 콘텐츠 또는 기본 시스템 종속성입니다. \<\/p \>에 오류가 있을 수 있습니다.|  
|기능:|**홈 페이지 컨트롤**|  
|사용:|텍스트의 도움말 뷰어 최상위 수준 노드 콘텐츠를 표시 하도록 지원 합니다.|  
|**요소**|**값**|  
|HomePageTitle|도움말 뷰어 홈|  
|HomePageIntroduction|\< p \> Microsoft 도움말 뷰어, Microsoft 도구, 제품, 기술 및 서비스를 사용 하 여 모든 사람에 대 한 정보의 꼭 필요한 리소스를 시작 합니다. 도움말 뷰어 사용 방법 및 참조 정보, 샘플 코드, 기술 문서 등에 액세스할 수 있습니다. 콘텐츠를 찾으려면 목차를 탐색 해야, 전체 텍스트 검색을 사용 하 여 또는 콘텐츠를 사용 하 여 키워드 인덱스 \<\/p \> 탐색|  
|HomePageContentInstallText|\< p \>\< b r \/ \> 사용 하 여는 \<는 href \= "{0}"이 \(가\) \\{1\\} \> 다음을 수행 하려면 콘텐츠 관리 \<\/a \> 탭: \< u l \>\< i \> 추가 콘텐츠를. \<\/l i \>\< i \> 확인 업데이트 하려면 사용자의 로컬 콘텐츠. \<\/l i \>\< i \>. \<\/l i \>\< \/ u l \>\< \/ p \>에서 콘텐츠 제거|  
|HomePageInstalledBooks|설치 된 책|  
|HomePageNoBooksInstalled|콘텐츠는 컴퓨터에서 발견 되었습니다.|  
|HomePageHelpSettings|도움말 콘텐츠 설정|  
|HomePageHelpSettingsText|\< p \> 현재 설정에는 로컬 도움말. 컴퓨터에 설치 된 콘텐츠를 표시 하는 도움말 뷰어 \< b r \/ \>의 Visual Studio 메뉴 모음에서 도움말 콘텐츠 소스를 변경 하려면 \< n style \= "{0}"이 \(가\) \> 도움말, 도움말 기본 설정 지정 \< \/ \>. \< b r \/ \>\< \/ p \>|  
|메가바이트|MB|  
  
 **branding.js**  
  
 Branding.js 파일 Visual Studio 도움말 뷰어 브랜딩 요소에서 사용 하는 JavaScript를 포함 합니다.  다음은 브랜딩 요소 및 관련 JavaScript 함수 목록입니다.  이 파일을 지역화할 수 있는 모든 문자열은이 파일의 맨 위에 있는 "지역화 가능한 문자열" 섹션에 정의 됩니다.  Note branding.js 파일 내에서 loc 문자열에 대 한 ICL 파일 만들어진 것입니다.  
  
||||  
|-|-|-|  
|**브랜딩 기능**|**JavaScript 함수**|**설명**|  
|Var...||변수 정의|  
|사용자 코드 언어|setUserPreferenceLang|인덱스에 매핑합니다 코드 언어를 \#|  
|설정 및 쿠키 값 가져오기|getCookie, setCookie||  
|상속 된 멤버|changeMembersLabel|상속 된 멤버를 확장\/축소 합니다.|  
|때 SelfBranded \= False|onLoad|인쇄 요청 인지 확인 하려면 쿼리 문자열을 읽습니다.  사용자 기본 설정된 탭에 초점을 모든 codesnippets를 설정 합니다.  인쇄 하는 경우 요청을 true로 isPrinterFriendly를 설정 합니다. 고대비 모드를 확인 합니다.|  
|코드 조각|addSpecificTextLanguageTagSet||  
||getIndexFromDevLang||  
||변경 탭||  
||setCodesnippetLang||  
||setCurrentLang||  
||CopyToClipboard||  
|CollapsibleArea|addToCollapsibleControlSet|목록에 모든 축소 가능 컨트롤 개체를 작성 합니다.|  
||CA\_Click|축소 가능한 영역의 상태에 따라, 어떤 이미지 및 제공 하는 텍스트를 정의 합니다.|  
|로고에 대 한 대비 지원|isBlackBackground\(\)|검은색 배경 인지 확인 하기 위해 호출.  정확한 경우에만 고대비 모드에 있습니다.|  
||isHighContrast\(\)|색이 지정 된 범위를 검색 고대비 모드 사용|  
||onHighContrast\(black\)|고대비 검색 되었을 때 호출 합니다.|  
|LST 기능|||  
||addToLanSpecTextIdSet\(id\)||  
||updateLST\(currentLang\)||  
||getDevLangFromCodeSnippet\(lang\)||  
|멀티미디어 기능|캡션 \(시작, 끝, 텍스트, 스타일\)||  
||findAllMediaControls\(normalizedId\)||  
||getActivePlayer\(normalizedId\)||  
||captionsOnOff\(id\)||  
||toSeconds\(t\)||  
||getAllComments\(node\)||  
||styleRectify \(스타일 이름, styleValue\)||  
||showCC\(id\)||  
||subtitle\(id\)||  
  
 **HTM 파일**  
  
 브랜딩 패키지에는 시나리오를 지 원하는 키 정보를 도움말 콘텐츠는 사용자가 설치 되어 있는 콘텐츠 집합을 설명 하는 섹션 및 항목의 로컬 집합에 항목을 찾을 수 없을 때를 알리는 페이지를 포함 하는 홈 예를 들어의 통신을 위한 HTM 파일 집합이 포함 되어 있습니다. 참고가 HTM 파일 제품당 수정할 수 있습니다.  ISO 셸 공급 업체를 기본 브랜딩 패키지를 가져와 이러한 페이지의 콘텐츠와 동작으로 변경 제품군의 필요성 수 있습니다.  이러한 파일 branding.xml 파일에서 해당 콘텐츠를 가져올 수 브랜딩 태그에 대 한 순서 대로 각 브랜딩 패키지를 참조 하십시오.  
  
||||  
|-|-|-|  
|**파일**|**기능**|**콘텐츠 원본 표시**|  
|homepage.htm|현재 설치 된 콘텐츠 및 해당 내용에 대 한 사용자에 게 제공 하는 적절 한 다른 메시지를 표시 하는 페이지입니다.  이 파일의 메타 데이터 특성 "Microsoft.Help.Id" 내용 추가 \= "\-1"이 콘텐츠는 로컬 콘텐츠 목차 맨 위에 있는으로 배치 합니다.||  
||\< META\_HOME\_PAGE\_TITLE\_ADD \/ \>|Branding.xml, \< HomePageTitle \> 태그|  
||\< HOME\_PAGE\_INTRODUCTION\_SECTION\_ADD \/ \>|Branding.xml, \< HomePageIntroduction \> 태그|  
||\< HOME\_PAGE\_CONTENT\_INSTALL\_SECTION\_ADD \/ \>|Branding.xml, \< HomePageContentInstallText \> 태그|  
||\< HOME\_PAGE\_BOOKS\_INSTALLED\_SECTION\_ADD \/ \>|Branding.xml 태그 \< HomePageInstalledBooks \>, \< HomePageNoBooksInstalled \> 책이 설치 된 응용 프로그램에서 생성 된 데이터는 섹션을 제목입니다.|  
||\< HOME\_PAGE\_SETTINGS\_SECTION\_ADD \/ \>|Branding.xml 태그 \< HomePageHelpSettings \> 섹션 텍스트 \< HomePageHelpSettingsText \> 섹션을 제목입니다.|  
|topiccorrupted.htm|하지만 몇 가지 이유를 표시할 수 없는 항목을 로컬 설정에 있는 경우 \(콘텐츠 손상\).||  
||\< META\_TOPIC\_CORRUPTED\_TITLE\_ADD \/ \>|Branding.xml, \< TopicCorruptedTitle \> 태그|  
||\< TOPIC\_CORRUPTED\_SECTION\_ADD \/ \>|Branding.xml, \< TopicCorruptedViewOnlineText \> 태그|  
|topicnotfound.htm|때 항목에에서 없는 로컬 콘텐츠 설정도 사용할 수 있는 온라인||  
||\< META\_TOPIC\_NOT\_FOUND\_TITLE\_ADD \/ \>|Branding.xml, \< TopicNotFoundTitle \> 태그|  
||\< META\_TOPIC\_NOT\_FOUND\_ID\_ADD \/ \>|Branding.xml, 태그 \< TopicNotFoundViewOnlineText \> \+ \< TopicNotFoundDownloadContentText \>|  
||\< TOPIC\_NOT\_FOUND\_SECTION\_ADD \/ \>|Branding.xml, \< TopicNotFoundText \> 태그|  
|contentnotinstalled.htm|제품에 대해 설치 된 로컬 콘텐츠가 없는 경우.||  
||\< META\_CONTENT\_NOT\_INSTALLED\_TITLE\_ADD \/ \>|Branding.xml, \< ContentNotInstalledTitle \> 태그|  
||\< META\_CONTENT\_NOT\_INSTALLED\_ID\_ADD \/ \>|Branding.xml, \< ContentNotInstalledDownloadContentText \> 태그|  
||\< CONTENT\_NOT\_INSTALLED\_SECTION\_ADD \/ \>|Branding.xml, \< ContentNotInstalledText \> 태그|  
  
 **CSS 파일**  
  
 Visual Studio 도움말 뷰어 브랜딩 패키지에는 일관성 있는 Visual Studio 도움말 콘텐츠 표시를 지원 하기 위해 두 개의 css 파일이 들어 있습니다.  
  
-   Where를 렌더링 하기 위한 css 요소를 포함 하는 Branding.css – SelfBranded \= false  
  
-   Where를 렌더링 하기 위한 css 요소를 포함 하는 Printer.css – SelfBranded \= false  
  
 Visual Studio 항목 프레젠테이션에 대 한 정의 포함 하는 Branding.css 파일 \(caveat는 패키지 서비스에서 Branding\_ \< 로캘 \>.mshc에 포함 된 branding.css 변경 될 수 있습니다\).  
  
 **그래픽 파일**  
  
 Visual Studio 콘텐츠는 다른 그래픽 뿐 아니라 Visual Studio 로고를 표시합니다.  Visual Studio 도움말 뷰어 브랜딩 패키지에 그래픽 파일의 전체 목록은 다음과 같습니다.  
  
||||  
|-|-|-|  
|**파일**|**기능**|**예제**|  
|clear.gif|축소 가능한 영역을 렌더링 하는 데 사용||  
|footer\_slice.gif|바닥글 표시||  
|info\_icon.gif|정보를 표시할 때 사용|고지 사항|  
|online\_icon.gif|이 아이콘은 온라인 링크와 연결 되도록||  
|tabLeftBD.gif|코드 조각 컨테이너를 렌더링 하는 데 사용||  
|tabRightBD.gif|코드 조각 컨테이너를 렌더링 하는 데 사용||  
|vs\_logo\_bk.gif|Branding.xml 태그 \< LogoFileName \>에 정의 된 같이 일반 대비 로고에 대 한 참조를 사용 합니다.  Visual Studio 제품에 대 한 로고 이름은 vs\_logo\_bk.gif입니다.||  
|vs\_logo\_wh.gif|Branding.xml 태그 \< LogoFileNameHC \>에 정의 된 대로 일반 높은 로고 참조에 사용 합니다.  Visual Studio 제품에 대 한 로고 이름은 vs\_logo\_wh.gif입니다.||  
|ccOff.png|선택 캡션 그래픽||  
|ccOn.png|선택 캡션 그래픽||  
|ImageSprite.png|축소 가능한 영역을 렌더링 하는 데 사용|확장 또는 축소 그래픽|  
  
### 배포 항목  
 이것은 매우 간단 하 고 빠른 자습서 MSHA 파일 및 cab 파일 집합이 구성 되어 설정 도움말 뷰어에서 콘텐츠 배포를 만들기 위한 또는 MSHC의 항목을 포함 합니다. MSHA cab 파일의 집합을 설명 하는 XML 파일 또는 MSHC 파일입니다. 도움말 뷰어 \(오류로 인해 콘텐츠 목록을 가져오는 데 MSHA를 읽을 수 있습니다. CAB 또는 합니다. MSHC 파일\) 로컬 설치에 사용할 수 있습니다.  
  
 도움말 뷰어 MSHA에 매우 기본적인 XML 스키마를 설명 하는 한 입문서입니다.  이 간략하게 설명 아래 예제에서는 구현 기록한 HelpContentSetup.msha 샘플링 합니다.  
  
 MSHA이이 입문서의 목적에 대 한 이름은 HelpContentSetup.msha \(파일의 이름은 원하는 대로 입력할 수, 확장명이. MSHA\)입니다. HelpContentSetup.msha \(아래 예제에서는\) cab 또는 MSHCs 사용할 수 있는 목록이 포함 되어야 합니다.  참고 파일 형식 \(MSHA 및 CAB 파일 형식의 조합을 지원 하지 않습니다\) MSHA 내에서 일치 해야 합니다. 각 CAB 또는 MSHC 있어야는 \< v class \= "패키지" \>... \< \/ div \> \(아래 예제 참조\).  
  
 참고: 아래 구현 예제에 포함 되어 있습니다 브랜딩 패키지. 이 필요한 Visual Studio 콘텐츠 렌더링 요소 및 콘텐츠 동작을 얻기 위해 포함 하는 데 중요 합니다.  
  
 샘플 HelpContentSetup.msha 파일: \(대체 "콘텐츠 집합 이름을 1" 및 "콘텐츠 집합 이름을 2" 등으로 파일 이름에 있습니다.\)  
  
```  
<html> <head /> <body class="vendor-book"> <div class="details"> <span class="vendor">Your Company</span> <span class="locale">en-us</span> <span class="product">Your Company Help Content</span> <span class="name">Your Company Help Content</span> </div> <div class="package-list"> <div class="package"> <span class="name">Your_Company _Content_Set_1</span> <span class="deployed">True</span> <a class="current-link" href="Your_Company _Content_Set_1.mshc">Your_Company _Content_Set_1.mshc </a> </div> <div class="package"> <span class="name">Your_Company _Content_Set_2</span> <span class="deployed">True</span> <a class="current-link"href=" Your_Company _Content_Set_2.mshc "> Your_Company _Content_Set_2.mshc </a> </div>.  
  
```  
  
1.  "C:\\SampleContent" 등과 같은 로컬 폴더를 만들으십시오  
  
2.  이 예제에 대 한 항목을 포함 하도록 MSHC 파일 사용 합니다.  MSHC 파일 확장명을.zip에서 변경 된 zip입니다. MSHC 합니다.  
  
3.  만들기는 텍스트 파일로 HelpContentSetup.msha 아래 \(메모장 파일을 만드는 데 사용 된\) 위에 명시 된 폴더에 저장 합니다 \(1 단계 참조\).  
  
 "브랜딩" 존재 하 고 고유한 하는 클래스입니다. 설치 된 콘텐츠는 브랜딩, 있으며는 MSHCs에 포함 된 콘텐츠 동작은 브랜딩 패키지에 포함 된 요소에 적절 한 지원 되도록 브랜딩 mshc이이 입문서에 포함 됩니다. 이렇게 하지 않으면 시스템은 복사한 \(설치\)의 일부분이 아닌 지원 항목에 대 한 콘텐츠 때 오류가 발생 합니다.  
  
 패키지를 브랜딩 Visual Studio를 가져오려면 작업 폴더를 C:\\Program Files \(x86\) \\Microsoft Help Viewer\\v2.1\\에서 Branding\_en US.mshc 파일을 복사 합니다.  
  
```html  
<html> <head /> <body class="vendor-book"> <div class="details"> <span class="vendor">Your Company</span> <span class="locale">en-us</span> <span class="product">Your Company Help Content</span> <span class="name">Your Company Help Content</span> </div> <div class="package-list"> <div class="package"> <span class="name">Your_Company _Content_Set_1</span> <span class="deployed">True</span> <a class="current-link" href="Your_Company _Content_Set_1.mshc">Your_Company _Content_Set_1.mshc </a> </div> <div class="package"> <span class="name">Your_Company _Content_Set_2</span> <span class="deployed">True</span> <a class="current-link"href=" Your_Company _Content_Set_2.mshc "> Your_Company _Content_Set_2.mshc </a> </div> <div class="package"> <span class="packageType">branding</span> <span class="name">Branding_en-US</span> <span class="deployed">True</span> <a class="current-link" href="Branding_en-US.mshc">Branding_en-US.mshc</a> </div> </div> </body> </html>  
  
```  
  
 **요약**  
  
 사용 하 고 위의 단계를 확장 합니다. Visual Studio 도움말 뷰어를 위해 해당 콘텐츠 집합을 배포 하는 Vsp 하면.  
  
### Visual Studio Shell \(통합 모드 및 격리 됨\)에 대 한 도움말 추가  
 **소개**  
  
 이 연습에서는 Visual Studio Shell 응용 프로그램에 도움말 콘텐츠를 통합 한 후 배포 하는 방법을 보여 줍니다.  
  
 **요구 사항**  
  
1.  [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)]  
  
2.  [Visual Studio 2013 Shell 재배포 가능 패키지를 격리](http://www.microsoft.com/visualstudio/11/downloads#vs-shell)  
  
 **개요**  
  
 [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] 셸의 버전이 [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] 응용 프로그램을 사용할 수 있는 IDE입니다. 이러한 응용 프로그램 확장 만드는 함께 격리 된 셸을 포함 합니다. 에 포함 된 격리 된 셸 프로젝트 템플릿을 사용 하 여는 [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] SDK로 확장 프로그램을 구축 합니다.  
  
 격리 된 셸 기반 응용 프로그램 및 해당 도움말을 만들기 위한 기본 단계:  
  
1.  가져오기는 [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] ISO Shell 재배포 가능 패키지 \(Microsoft 다운로드\).  
  
2.  Visual Studio에서 예를 들어 격리 된 셸 기반 하는 도움말 확장,이 연습의 뒷부분에서 설명 하는 Contoso 지원 확장을 만듭니다.  
  
3.  확장 및 ISO 셸에 MSI \(응용 프로그램 설치\) 배포에 재배포 가능 패키지를 래핑하십시오. 이 연습에서는 설치 단계를 포함 하지 않습니다.  
  
 Visual Studio 콘텐츠 저장소를 만듭니다. 통합 셸 시나리오에 대 한 제품 카탈로그 이름을 Visual Studio12을 다음과 같이 변경 합니다.  
  
-   C:\\ProgramData\\Microsoft\\HelpLibrary2\\Catalogs\\VisualStudio12 폴더를 만듭니다.  
  
-   CatalogType.xml 라는 파일을 만들고 폴더에 추가 합니다. 파일에 다음 코드 줄을 포함 되어야 합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?> <catalogType>UserManaged</catalogType>  
    ```  
  
 레지스트리에서 콘텐츠 저장소를 정의 합니다. Integrated Shell에 대 한 VisualStudio12 제품 카탈로그 이름을 변경 합니다.  
  
-   HKLM\\SOFTWARE\\Wow6432Node\\Microsoft\\Help\\v2.1\\Catalogs\\VisualStudio12  
  
     키: LocationPath 문자열 값: C:\\ProgramData\\Microsoft\\HelpLibrary2\\Catalogs\\VisualStudio12\\  
  
-   HKLM\\SOFTWARE\\Wow6432Node\\Microsoft\\Help\\v2.1\\Catalogs\\VisualStudio12\\en\-US  
  
     키: CatalogName 문자열 값: [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] 설명서  
  
 **프로젝트 만들기**  
  
 격리 된 셸 확장을 만들려면:  
  
1.  Visual Studio에서 아래 **파일**, 선택 **새 프로젝트**, 아래에서 **기타 프로젝트 형식** 선택 **확장성**, 를 선택한 다음  **Visual Studio Shell 격리 된**합니다. 프로젝트 이름을 `ContosoHelpShell`\) Visual Studio Isolated Shell 템플릿을 기반으로 하는 확장성 프로젝트를 만듭니다.  
  
2.  솔루션 탐색기에서 ContosoHelpShellUI 프로젝트 리소스 파일 폴더에서 ApplicationCommands.vsct를 엽니다. 이 줄 \("No\_Help" 검색\) 주석 처리 되어 있는지 확인 합니다. `<!-- <define name=“No_HelpMenuCommands”/> -->`  
  
3.  F5 키를 컴파일하고 실행 하려면 선택 **디버그**합니다. 격리 된 셸 IDE의 실험적 인스턴스를 선택 된 **도움말** 메뉴. 다음 사항을 확인은 **도움말 보기**, **제거 도움말 콘텐츠 추가 및**, 및 **도움말 기본 설정 지정** 명령이 나타납니다.  
  
4.  솔루션 탐색기에서 ContosHelpShell 프로젝트 셸 사용자 지정 폴더에서 ContosoHelpShell.pkgdef를 엽니다. Contoso 도움말 카탈로그를 정의 하려면 다음 줄을 추가 합니다.  
  
    ```  
    [$RootKey$\Help] "Product"="Contoso" "Catalog"="Contoso" “Version"="100" "BrandingPackage"="ContosoBrandingPackage.mshc"  
    ```  
  
5.  솔루션 탐색기에서 ContosHelpShell 프로젝트 셸 사용자 지정 폴더에서 ContosoHelpShell.Application.pkgdef를 엽니다. F1 도움말을 사용 하려면 다음 줄을 추가 합니다.  
  
    ```  
    // F1 Help Provider [$RootKey$\HelpProviders\{C99BDC23-FF29-46bf-9658-ADD634CCAED8}] "Name"="13407" "Package"="{DA9FB551-C724-11d0-AE1F-00A0C90FFFC3}" @="Help3 Provider" [$RootKey$\HelpProviders] @="{C99BDC23-FF29-46bf-9658-ADD634CCAED8}" [$RootKey$\Services\{C99BDC23-FF29-46bf-9658-ADD634CCAED8}] "Name"="Help3 Provider" @="{4A791146-19E4-11D3-B86B-00C04F79F802}"  
    ```  
  
6.  솔루션 탐색기의 ContosoHelpShell 솔루션의 상황에 맞는 메뉴에서 선택 된 **속성** 메뉴 항목입니다. 아래에서 **구성 속성**, 선택, **Configuration Manager**합니다. 에 **구성** 열에서 모든 "Debug" 값 "릴리스"로 변경 합니다.  
  
7.  솔루션을 빌드합니다. 다음 섹션에서 사용 되는 릴리스 폴더에 파일의 집합을 만듭니다.  
  
 배포 하는 경우이 테스트 합니다.  
  
1.  컴퓨터에서 다운로드 한 ISO 셸 \(위쪽\)을 설치 하는 Contoso 배포 하는 합니다.  
  
2.  \\\\Program Files \(x86\)에 폴더를 만들고 \\를 하 고 이름을 `Contoso`합니다.  
  
3.  내용을 ContosoHelpShell 릴리스 폴더에서 \\\\Program Files \(x86\) \\Contoso\\ 폴더로 복사 합니다.  
  
4.  레지스트리 편집기를 선택 하 여 시작  **실행** 에 **시작** 메뉴와 입력 `Regedit`합니다. 레지스트리 편집기에서 선택 **파일**, 차례로 **가져오기**합니다. ContosoHelpShell 프로젝트 폴더를 찾습니다. ContosoHelpShell 하위 폴더에 ContosoHelpShell.reg를 선택 합니다.  
  
5.  콘텐츠 저장소를 만듭니다.  
  
     ISO 셸에\-Contoso 콘텐츠 저장소 C:\\ProgramData\\Microsoft\\HelpLibrary2\\Catalogs\\ContosoDev12 만들기  
  
     에 대 한 [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] 통합 셸을 C:\\ProgramData\\Microsoft\\HelpLibrary2\\Catalogs\\VisualStudio12 폴더 만들기  
  
6.  CatalogType.xml 만들고 포함 된 콘텐츠 저장소 \(이전 단계\)를 추가 합니다.  
  
    ```  
    <?xml version="1.0" encoding="UTF-8"?> <catalogType>UserManaged</catalogType>  
    ```  
  
7.  다음 레지스트리 키를 추가 합니다.  
  
     HKLM\\SOFTWARE\\Wow6432Node\\Microsoft\\Help\\v2.1\\Catalogs\\VisualStudio12Key LocationPath 문자열 값입니다.:  
  
     에 대 한 ISO 셸:  
  
     C:\\ProgramData\\Microsoft\\HelpLibrary2\\Catalogs\\VisualStudio12\\  
  
     [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] 통합된 셸:  
  
     C:\\ProgramData\\Microsoft\\HelpLibrary2\\Catalogs\\VisualStudio12\\\\en\-US  
  
     키: CatalogName 문자열 값: [!INCLUDE[vs_dev12](../../data-tools/includes/vs_dev12_md.md)] 설명서입니다. ISO 셸에 대 한 카탈로그의 이름입니다.  
  
8.  \(Cab 또는 MSHC 및 MSHA\) 콘텐츠를 로컬 폴더에 복사 합니다.  
  
9. 통합형 셸 명령줄 예 콘텐츠 저장소를 테스트 합니다. ISO 셸에 대 한 제품에 맞게 적절히 카탈로그 및 launchingApp 값을 변경 합니다.  
  
     "C:\\Program Files \(x86\) \\Microsoft Help Viewer\\v2.1\\HlpViewer.exe" \/catalogName VisualStudio12 \/helpQuery 메서드 \= "페이지 및 id ContosoTopic0 \=" Microsoft visual Studio, 12.0 \/launchingApp  
  
10. \(Contoso 응용 프로그램 루트\)에서 Contoso 응용 프로그램을 시작 합니다. ISO 셸 내에서 선택 된 **도움말** 메뉴 항목을 변경은 **도움말 기본 설정 지정** 를 **사용 하 여 로컬 도움말**.  
  
11. Shell에서 선택 된 **도움말** 메뉴 항목을 다음 **도움말 보기**합니다. 로컬 도움말 뷰어를 시작 해야 합니다.**콘텐츠 관리** 탭을 선택합니다. 아래에서 **설치 원본**, 선택 된 **디스크** 옵션 단추입니다. 선택 된 **...** 단추와 Contoso 콘텐츠 \(위 단계에서 로컬 폴더에 복사\)를 포함 하는 로컬 폴더를 찾습니다. HelpContentSetup.msha를 선택 합니다. Contoso는 이제 책 선택 항목에 있는 책으로 설정할 수도 있습니다. 선택 **추가**, 를 선택한 다음는 **업데이트** 단추 \(오른쪽 아래\).  
  
12. Contoso IDE 내에서 F1 기능을 테스트 하려면 F1 키를 선택 합니다.  
  
### 추가 리소스  
 런타임 API에 대 한 참조 [Windows API 도움말](http://msdn.microsoft.com/library/windows/desktop/hh447318\(v=vs.85\).aspx)합니다.  
  
 API 도움말을 활용 하는 방법에 대 한 자세한 내용은 참조 [도움말 뷰어 코드 예제에서는](http://visualstudiogallery.msdn.microsoft.com/f08f296f-7076-4aec-8da3-8f0fbe04461e)  
  
 사용 하 여 이러한 구성 요소에 대 한 피드백을 제공 하려면 [Microsoft Connect](http://connect.microsoft.com/)합니다.  
  
 기능 제안 를 보고 해 주십시오 [Microsoft 사용자 음성](http://visualstudio.uservoice.com/forums/121579-visual-studio)  
  
 추가 도움말을 얻으려면 시도 [MSDN 개발자 설명서 및 도움말 시스템 포럼](http://social.msdn.microsoft.com/Forums/devdocs/threads)  
  
 주요 문제에 대 한 업데이트를 참조 하십시오.는 [도움말 뷰어 Readme](http://go.microsoft.com/fwlink/?LinkID=231397&clcid=0x409)  
  
 도움말 뷰어 PM 팀을 직접 연락 하 hlpfdbk@microsoft.com에 전자 메일 보내기