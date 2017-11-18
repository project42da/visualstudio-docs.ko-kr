---
title: "문자열 시각화 도우미에 문자열을 보기 | Microsoft Docs"
ms.custom: 
ms.date: 07/11/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.stringviewer
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- string visualizer
- visualizers, string
ms.assetid: 080fd8f1-72b0-461f-8451-3c84d5dc51df
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a14b9f68eb2f77ed248c82b81ce7063547e58bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="view-strings-in-a-string-visualizer-in-visual-studio"></a>Visual Studio에서 문자열 시각화 도우미에 문자열을 봅니다.
디버깅 하는 동안 너무 길어 데이터 팁 또는 디버거 창에서 볼 수 있는 보기 문자열을 문자열 시각화 도우미를 열 수 있습니다. 대부분의 시나리오에서 시각화 도우미 하는 데 도움이 잘못 된 형식의 문자열을 식별 합니다.

표준 기본 제공 문자열 시각화 도우미는 일반 텍스트, XML, HTML 및 JSON을 포함 합니다. Windows와 같은 디버거에 표시 되는 WPF 개체와 같은 다른 몇 가지 유형에 **자동** 창에서 시각화 도우미를 열 수도 있습니다.

## <a name="open-a-string-visualizer"></a>문자열 시각화 도우미를 열려면

일반 텍스트, XML, HTML 또는 JSON 문자열을 보려면 돋보기 아이콘을 클릭 ![VisualizerIcon](../debugger/media/dbg-tips-visualizer-icon.png "시각화 도우미 아이콘") 는 문자열 값을 포함 하는 변수를 가리키면 됩니다. 돋보기 아이콘을 확인 하려면 디버거에서 일시 중지 해야 합니다.

![문자열 시각화 도우미를 열고](../debugger/media/dbg-tips-string-visualizers.png "OpenStringVisualizer")

## <a name="view-string-data"></a>문자열 데이터 보기

**식** 문자열 시각화 도우미에서 필드에는 현재 변수 또는 식 위로 가져갈 디버거에서 표시 합니다.

**값** 필드 문자열 값을 표시 합니다. 텍스트 시각화 도우미에서는 일반 텍스트를 보여 줍니다.

빈 **값** 특정 시각화 도우미는 문자열 형식을 인식할 수 없습니다 나타냅니다. XML 시각화 도우미는 빈 값을 표시 하는 예를 들어 **값** 간단한 텍스트 문자열 (XML 태그 없음) 또는 JSON 형식 문자열에 대 한 합니다. 시각화 도우미에서 인식할 수 없는 문자열을 보는 데 필요한 경우 텍스트 시각화 도우미를 사용 합니다.

### <a name="view-json-string-data"></a>JSON 문자열 데이터 보기

올바른 형식의 JSON 문자열을 JSON 시각화 도우미에서 다음 그림과 유사 하 게 표시 됩니다. 잘못 된 형식의 JSON 오류 아이콘 (또는 인식할 수 없는 경우 공백)에 표시 될 수 있습니다.

![JSON 문자열 시각화 도우미](../debugger/media/dbg-tips-string-visualizer-json.png "JSON 문자열 시각화 도우미")

### <a name="view-xml-string-data"></a>XML 문자열 데이터 보기

올바른 형식의 XML 문자열로 XML 시각화 도우미에서 다음 그림과 유사 하 게 표시 됩니다. 잘못 된 XML은 XML 태그 (또는 인식할 수 없는 경우 공백) 없이도 표시할 수 있습니다.

![XML 문자열 시각화 도우미](../debugger/media/dbg-string-visualizers-xml.png "XML 문자열 시각화 도우미")

### <a name="view-html-string-data"></a>문자열 데이터를 HTML 보기

올바른 형식의 HTML 문자열로 표시 되는 문자열을 브라우저에서 렌더링 됩니다 다음 그림에 나와 있는 것 처럼 보기와 비슷한 나타납니다. 잘못 된 HTML 일반 텍스트로 표시 될 수 있습니다.

![HTML 문자열 시각화 도우미](../debugger/media/dbg-string-visualizers-html.png "HTML 문자열 시각화 도우미")

## <a name="see-also"></a>참고 항목  
 [사용자 지정 시각화 도우미 (C#, Visual Basic) 만들기](../debugger/create-custom-visualizers-of-data.md)