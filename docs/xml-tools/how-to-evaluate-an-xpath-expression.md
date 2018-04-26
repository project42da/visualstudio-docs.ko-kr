---
title: '방법: XPath 식 계산'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2956e0c19e7cf50fdde39765bc5b26112986b84
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-evaluate-an-xpath-expression"></a>방법: XPath 식 계산

된 XPath 식을 계산할 수 있습니다는 **간략 한 조사식** 대화 상자. XPath 식은 W3C XPath 1.0 권장 사항에 따라 유효한 식이어야 합니다. 현재 XSLT 컨텍스트-즉,는 `self::node()` 에서 노드는 **지역** 창-XPath 식에 대 한 계산 컨텍스트를 제공 합니다.

 다음 목록에서는 XPath 식을 계산할 때 지원되는 함수를 설명합니다.

-   기본 제공 XPath 함수가 지원됩니다.

-   기본 제공 XSLT 함수는 지원되지 않습니다.

-   사용자 정의 함수는 지원되지 않습니다.

> [!NOTE]
> 다음 절차에서 belowAvg.xsl 및 books.xml 파일을 사용 하는 [연습: XSLT 스타일 시트를 디버깅](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md) 항목입니다.

## <a name="to-evaluate-an-xpath-expression"></a>XPath 식을 계산하려면

1.  `xsl:if` 시작 태그에 중단점을 삽입합니다.

2.  클릭는 **XSL 디버깅** XML 편집기 도구 모음 단추입니다.

     디버거가 시작되고 `xsl:if` 태그에서 중단됩니다.

3.  마우스 오른쪽 단추로 클릭 하 고 선택 **간략 한 조사식**합니다.

     **간략 한 조사식** 대화 상자가 표시 됩니다.

4.  입력 `./price/text()` 에 **식** 필드는 **간략 한 조사식** 대화 상자와 클릭 **다시 평가**합니다.

     현재 book 노드의 가격이에 표시 된 **값** 상자입니다.

5.  XPath 식을 변경 `./price/text() < $bookAverage` 클릭 **재평가**합니다.

     **값** 상자 XPath 식은로 평가 되었음이 나타납니다 `true`합니다.

## <a name="see-also"></a>참고 항목

- [XSLT 디버그](../xml-tools/debugging-xslt.md)