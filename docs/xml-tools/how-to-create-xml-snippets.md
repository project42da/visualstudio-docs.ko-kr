---
title: "방법: XML 조각 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8556dd7-1382-4af7-ba80-3e873c9416be
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 05962d6806631bdfa9b873038ec85cdf9969d55c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-xml-snippets"></a>방법: XML 조각 만들기
XML 편집기를 사용하여 새 XML 조각을 만들 수 있습니다. 이 편집기에는 새 XML 조각을 만들기 위한 상용구 조각인 "Snippet"이라는 XML 조각이 들어 있습니다.  
  
## <a name="to-create-a-new-xml-snippet"></a>새 XML 조각을 만들려면  
 새 XML 코드 조각을 만들려면 새 XML 파일을 사용 하 여는 **조각 삽입** 기능입니다.  
  
1.  에 **파일** 메뉴를 클릭 **새로** 클릭 하 고 **파일**합니다.  
  
2.  클릭 **XML 파일** 클릭 하 고 **열려**합니다.  
  
3.  편집기 창에서 마우스 오른쪽 단추로 클릭 하 고 선택 **조각 삽입**합니다.  
  
4.  선택 **조각** 목록 및 ENTER 키를 누릅니다.  
  
5.  원하는 대로 새 조각을 변경합니다.  
  
6.  **파일** 메뉴 선택 **XMLFile.xml 저장**합니다.  
  
     **이름으로 파일 저장** 대화 상자가 표시 됩니다.  
  
7.  새 조각의 이름을 입력 하 고 선택 **조각 파일** 에서 **파일 형식** 드롭다운 창.  
  
8.  사용 하 여는 **저장** 하는 파일 위치를 My Documents\Visual Studio 2005 \code Snippets\XML\My XML Snippets 폴더로 변경 하 고 다음 키를 누릅니다 드롭 다운 목록 **저장**합니다.  
  
## <a name="snippet-description"></a>조각 설명  
 이 단원에서는 상용구 조각의 몇 가지 핵심 요소에 대해 설명합니다. XML 조각에서 사용 하는 스키마 요소에 대 한 자세한 내용은 참조 [코드 조각 스키마 참조](../ide/code-snippets-schema-reference.md)합니다.  
  
### <a name="snippettype-element"></a>SnippetType 요소  
 편집기에서는 두 가지 조각 형식을 지원합니다.  
  
```xml
<SnippetTypes>  
  <SnippetType>SurroundsWith</SnippetType>  
  <SnippetType>Expansion</SnippetType>  
</SnippetTypes>  
```  
  
 `Expansion` 형식을 호출할 때 조각이 나타나는지 여부를 결정은 **조각 삽입** 명령입니다. `SurroundsWith` 형식을 호출할 때 조각이 나타나는지 여부를 결정은 **포함** 명령입니다.  
  
### <a name="code-element"></a>Code 요소  
 `Code` 요소는 조각을 호출할 때 삽입할 XML 텍스트를 정의합니다.  
  
> [!NOTE]
>  XML 조각 텍스트는 `<![CDATA[...]]>` 섹션에 포함되어야 합니다.  
  
 다음은 상용구 조각으로 만든 `Code` 요소입니다.  
  
```xml
<Code Language="XML">  
  <![CDATA[<test>  
  <name>$name$</name>  
  $selected$ $end$</test>]]>  
</Code>  
```  
  
 `Code` 요소에는 변수 3개가 포함됩니다.  
  
-   $name$은 사용자 정의 변수입니다. 이 변수는 `name` 요소를 만듭니다. 이 요소는 기본값이 "name"이며 편집 가능한 값을 가집니다. 사용자 정의 변수는 `Literal` 요소를 사용하여 정의합니다.  
  
-   $selected$는 미리 정의된 변수입니다. 이 변수는 조각을 호출하기 전에 XML 편집기에서 선택한 텍스트를 나타냅니다. 이 변수는 선택한 텍스트를 포함하는 코드 조각에서 이 텍스트가 나타나는 위치를 결정합니다.  
  
-   $end$는 미리 정의된 변수입니다. Enter 키를 눌러 코드 조각 필드 편집을 마치면 이 변수는 캐럿(^)이 이동되는 위치를 결정합니다.  
  
 위의 `Code` 요소는 다음 XML 텍스트를 삽입합니다.  
  
```xml
<test>  
  <name>name</name>  
</test>  
```  
  
 name 요소 값은 편집 가능한 영역으로 표시됩니다.  
  
### <a name="literal-element"></a>Literal 요소  
 `Literal` 요소를 사용하면 대체 텍스트를 파일에 삽입한 후 사용자 지정할 수 있는 대체 텍스트를 식별할 수 있습니다. 예를 들어, 리터럴 문자열, 숫자 값 및 몇 가지 변수 이름을 리터럴로 선언할 수 있습니다. XML 조각에서 원하는 수만큼 리터럴을 정의할 수 있으며 XML 조각 내에서 이 리터럴을 여러 번 참조할 수 있습니다. 다음은 기본값이 "name"인 $name$ 변수를 정의하는 `Literal` 요소의 예제입니다.  
  
```xml
<Literal>  
  <ID>name</ID>  
  <Default>name</Default>  
</Literal  
```  
  
 리터럴은 함수를 참조할 수도 있습니다. 명명 된 함수를 포함 하는 XML 편집기 **LookupPrefix**합니다. **LookupPrefix** 함수가 코드이 조각에서 호출 되 고 있는 경우 해당 네임 스페이스에 대해 정의 된 네임 스페이스 접두사를 반환 및 콜론 (:)을 포함 하는 XML 문서에 대 한 위치에서 지정된 된 네임 스페이스 URI 조회 합니다. 에 해당 이름입니다. 다음은의 예는 `Literal` 요소를 사용 하는 **LookupPrefix** 함수입니다.  
  
```xml
<Literal Editable="false">  
   <ID>prefix</ID>  
   <Function>LookupPrefix("namespaceURI")</Function>  
</Literal>  
```  
  
 그런 다음 XML 조각에서 $prefix$ 변수를 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 조각](../xml-tools/xml-snippets.md)   
 [방법: XML 조각 사용](../xml-tools/how-to-use-xml-snippets.md)   
 [방법: XML 스키마에서 XML 조각 생성](../xml-tools/how-to-generate-an-xml-snippet-from-an-xml-schema.md)