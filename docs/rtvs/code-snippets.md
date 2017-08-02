---
title: "Visual Studio용 R 도구를 사용한 코드 조각 | Microsoft Docs"
ms.custom: 
ms.date: 4/28/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-r
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bf4f87-e276-40cd-bc17-3dfb47ef1870
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 7a873df77756e5a957d327049566c8e0db1f3a8a
ms.openlocfilehash: 033a06b276b8a31e6c69b0eff68ee3f76dda1042
ms.contentlocale: ko-kr
ms.lasthandoff: 05/12/2017

---

# <a name="code-snippets"></a>코드 조각

Visual Studio의 코드 조각은 임의 길이의 코드 블록을 빠르게 삽입하여 비슷한 코드를 반복해서 다시 입력하지 않도록 도와주는 바로 가기를 제공합니다. RTVS(Visual Studio용 R 도구)는 Visual Studio 컬렉션에 수십 개의 유용한 R 코드 조각을 추가합니다.

코드 조각을 삽입하려면 코드 조각의 약식 이름을 입력하고(IntelliSense가 제공됨) Tab 키를 눌러 삽입합니다.

몇 가지 간단한 예제:

- `=`를 입력하고 Tab 키를 누르면 RTVS에서 이 조각을 `<-` 대입 연산자로 확장합니다.
- `>`을 입력하고 Tab 키를 누르면 RTVS에서 이 조각을 `%>%` 파이프 연산자로 확장합니다.

코드 조각은 문자의 단순한 문자 완성보다 훨씬 더 큰 의미가 있을 수 있습니다. 예를 들어 코드 조각을 사용하여 `read.csv` 함수로 CSV 파일을 읽는 이 코드 조각과 같이 복잡한 함수 호출의 매개 변수 이름을 기억할 필요가 없습니다.

![코드 조각을 사용하여 read.csv 호출을 삽입하는 애니메이션](~/rtvs/media/code-snippet-expansion.gif)

이 경우 `readc`를 입력하면 IntelliSense가 완성 목록을 표시합니다. 드롭다운에서 해당 완성을 선택하고 Tab 키를 누르면 `readc`가 선택되고 Tab 키를 다시 누르면 코드 조각이 확장됩니다. 이 이유로 코드 조각 확장은 보통 “코드 조각을 입력하고 Tab 키를 두 번 누르는 것”과 비슷합니다. 대부분의 경우 첫 번째 Tab 키는 IntelliSense 선택을 완성하고 두 번째 Tab 키는 확장을 트리거합니다.

모든 사용 가능한 코드 조각을 보려면 **도구 > 코드 조각 관리자...** 대화 상자(Ctrl+K,B)를 열고 **언어**로 **R**을 선택합니다. 그룹을 확장하고 개별 코드 조각을 선택하여 설명과 바로 가기 텍스트를 표시합니다.

![R에 대한 코드 조각 대화 상자](~/rtvs/media/code-snippet-dialog.png)

사용자 지정 코드 조각을 만들려면 [연습: 코드 조각 만들기](../ide/walkthrough-creating-a-code-snippet.md)의 지침을 따릅니다. 결국 코드 조각은 XML 파일입니다. 예를 들어 다음은 파이프 연산에 대한 코드 조각입니다(바로 가기 `>`).

코드 조각은 XML 파일입니다. 다음은 파이프 연산자에 대한 코드 조각입니다.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
  <CodeSnippet Format="1.0.0">
    <Header>
      <Title>Dplyr pipe</Title>
      <Shortcut>&gt;</Shortcut>
      <Description>Code snippet for '%&gt;%' operator</Description>
      <Author>Microsoft Corporation</Author>
      <SnippetTypes>
        <SnippetType>Expansion</SnippetType>
       </SnippetTypes>
    </Header>
    <Snippet>
      <Code Language="R">
        <![CDATA[ %>% $end$]]>
      </Code>
    </Snippet>
  </CodeSnippet>
</CodeSnippets>
```

모든 코드 조각에 대한 XML 파일은 RTVS와 함께 설치됩니다. **코드 조각 관리자**의 **위치** 필드에는 경로가 제공됩니다. GitHub의 [src/Package/Impl/Snippets](https://github.com/Microsoft/RTVS/tree/master/src/Package/Impl/Snippets) 아래 RTVS 소스 코드에서도 코드 조각을 찾을 수 있습니다.
