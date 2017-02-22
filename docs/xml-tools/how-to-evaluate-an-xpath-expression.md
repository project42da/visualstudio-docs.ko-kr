---
title: "방법: XPath 식 계산 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
caps.latest.revision: 2
caps.handback.revision: 2
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: XPath 식 계산
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**간략한 조사식** 대화 상자를 사용하여 XPath 식을 계산할 수 있습니다.XPath 식은 W3C XPath 1.0 권장 사항에 따라 유효한 식이어야 합니다.현재 XSLT컨텍스트, 즉 **지역** 창의 `self::node()` 노드에서는 XPath 식에 대한 계산 컨텍스트를 제공합니다.  
  
 다음 목록에서는 XPath 식을 계산할 때 지원되는 함수를 설명합니다.  
  
-   기본 제공 XPath 함수가 지원됩니다.  
  
-   기본 제공 XSLT 함수는 지원되지 않습니다.  
  
-   사용자 정의 함수는 지원되지 않습니다.  
  
> [!NOTE]
>  다음 프로시저에서는 [연습: XSLT 스타일시트 디버깅](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md) 항목의 belowAvg.xsl 및 books.xml 파일을 사용합니다.  
  
### XPath 식을 계산하려면  
  
1.  `xsl:if` 시작 태그에 중단점을 삽입합니다.  
  
2.  XML 편집기 도구 모음에서 **XSL 디버깅** 단추를 클릭합니다.  
  
     디버거가 시작되고 `xsl:if` 태그에서 중단됩니다.  
  
3.  마우스 오른쪽 단추를 클릭하고 **간략한 조사식**을 선택합니다.  
  
     **간략한 조사식** 대화 상자가 표시됩니다.  
  
4.  **간략한 조사식** 대화 상자의 **식** 필드에 `./price/text()`를 입력하고 **다시 계산**을 클릭합니다.  
  
     현재 book 노드의 가격이 **값** 상자에 나타납니다.  
  
5.  XPath 식을 `./price/text() < $bookAverage`로 변경하고 **다시 계산**을 클릭합니다.  
  
     **값** 상자에 XPath 식이 `true`로 평가되었음이 나타납니다.  
  
## 참고 항목  
 [XSLT 디버깅](../xml-tools/debugging-xslt.md)