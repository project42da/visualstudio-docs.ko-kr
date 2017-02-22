---
title: "방법: 기호 정보 직렬화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.ToolsOptionsPages.Performance.General"
helpviewer_keywords: 
  - "프로파일링 도구, 기호 정보 직렬화"
  - "성능 도구, 기호 정보 직렬화"
ms.assetid: 9e0da706-6325-4073-83d1-aeab3b7c137a
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 기호 정보 직렬화
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

응용 프로그램을 분석하는 데 필요한 기호를 serialize할 수 있습니다.  기호를 serialize하면 .vsp 파일에 기호가 추가됩니다.  .vsp 파일에 기호 정보를 추가하면 다른 사용자가 원래 기호에 액세스하지 않고도 성능 보고서를 분석할 수 있습니다.  기호를 serialize하지 않은 경우에는 원래 계측된 .exe 및 .pdb 파일이 있어야만 .vsp 파일을 분석할 수 있습니다.  
  
### 기호 정보를 자동으로 serialize하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
     **옵션** 대화 상자가 표시됩니다.  
  
2.  **성능 도구**를 클릭합니다.  
  
3.  **일반 설정** 아래에서 **자동으로 기호 정보 serialize**를 선택합니다.  
  
## 참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [방법: Windows 기호 정보 참조](../profiling/how-to-reference-windows-symbol-information.md)   
 [How to: Save Analyzed Report Files](http://msdn.microsoft.com/ko-kr/0340ddde-caf4-48ac-8af3-d15dcdade556)