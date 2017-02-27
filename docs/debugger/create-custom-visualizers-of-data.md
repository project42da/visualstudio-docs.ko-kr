---
title: "시각화 도우미 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.visualizer.troubleshoot"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버거, 시각화 도우미"
  - "시각화 도우미"
ms.assetid: c24c006f-f2ac-429f-89db-677fc0c6e1ea
caps.latest.revision: 28
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 28
---
# 시각화 도우미
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

시각화 도우미는 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 디버거 사용자 인터페이스의 구성 요소입니다.  *시각화 도우미*는 변수나 개체의 데이터 형식에 적합한 방식으로 변수나 개체를 표시하기 위한 대화 상자 또는 다른 인터페이스를 만듭니다.  예를 들어 HTML 시각화 도우미는 HTML 문자열을 해석하고 브라우저 창에서와 마찬가지로 그 결과를 표시합니다. 비트맵 시각화 도우미는 비트맵 구조를 해석하고 그 구조가 표현하는 그래픽을 표시합니다.  일부 시각화 도우미에서는 데이터를 볼 수 있을 뿐만 아니라 수정할 수도 있습니다.  
  
 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 디버거에는 6가지 표준 시각화 도우미가 포함되어 있습니다.  이 6가지 표준 시각화 도우미는 문자열 개체에 사용되는 텍스트, HTML, XML 및 JSON 시각화 도우미와 WPF 개체 시각적 트리의 속성을 표시하는 WPF 트리 시각화 도우미, 그리고 DataSet, DataView 및 DataTable 개체에 사용되는 데이터 집합 시각화 도우미입니다.  향후 Microsoft Corporation의 추가 시각화 도우미를 다운로드할 수 있으며 타사와 커뮤니티의 시각화 도우미도 사용 가능합니다.  또한 자신만의 시각화 도우미를 직접 작성하여 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 디버거에 설치할 수 있습니다.  
  
> [!NOTE]
>  **스토어** 앱에서는 표준 텍스트, HTML, XML 및 JSON 시각화 도우미만 지원됩니다.  사용자가 만든 사용자 지정 시각화 도우미는 지원되지 않습니다.  
  
 시각화 도우미는 디버거에 돋보기 모양의 아이콘으로 표시됩니다.  디버거 변수 창이나 **간략한 조사식** 대화 상자에서 **DataTip**에 돋보기 아이콘이 나타나면 이 돋보기 아이콘을 클릭하여 상응하는 개체의 데이터 형식에 적합한 시각화 도우미를 선택할 수 있습니다.  
  
 Compact Framework에서는 시각화 도우미가 지원되지 않습니다.  
  
> [!NOTE]
>  디버거 시각화 도우미에는 부분 신뢰 응용 프로그램에 허용되는 것보다 많은 권한이 필요합니다.  따라서 부분 신뢰 코드에서 중지하면 시각화 도우미가 로드되지 않습니다.  시각화 도우미를 사용하여 디버깅하려면 완전 신뢰 코드를 실행해야 합니다.  
  
## 단원 내용  
 [방법: 시각화 도우미 작성](../debugger/how-to-write-a-visualizer.md)  
  
 [연습: C\#에서 시각화 도우미 작성](../debugger/walkthrough-writing-a-visualizer-in-csharp.md)  
  
 [방법: 시각화 도우미 설치](../debugger/how-to-install-a-visualizer.md)  
  
 [방법: 시각화 도우미 테스트 및 디버깅](../debugger/how-to-test-and-debug-a-visualizer.md)  
  
 [시각화 도우미 API 참조](../debugger/visualizer-api-reference.md)  
  
## 관련 단원  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)