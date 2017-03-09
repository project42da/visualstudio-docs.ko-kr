---
title: "표시 뷰 | Microsoft Docs"
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
  - "vs.performance.view.marks"
helpviewer_keywords: 
  - "프로파일링 도구 보고서, 표시 뷰"
  - "프로파일링 도구, 표시 뷰"
ms.assetid: b2773344-8081-4116-85a1-58f770448f6a
caps.latest.revision: 18
caps.handback.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 표시 뷰
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

표시 뷰는 샘플링 및 응용 프로그램에 삽입 된 ETW 이벤트를 표시 합니다.  
  
 보고서에 미리 채워지는 기본 표시는 프로그램 시작과 프로그램 끝에 레이블을 지정합니다.  
  
 자동으로 생성되는 표시의 Windows 카운터 데이터도 이 뷰에 표시됩니다.  자세한 내용은 [방법: Windows 카운터 데이터 수집](../profiling/how-to-collect-windows-counter-data.md)을 참조하십시오.  
  
 두 표시 간에 필터를 만들려면 표시를 선택하고 마우스 오른쪽 단추를 클릭한 다음 **표시에 대한 필터 추가** 또는 **타임스탬프에 대한 필터 추가**를 클릭합니다.  
  
 다음 표에는 표시 뷰에서 사용할 수 있는 열의 정의가 표시되어 있습니다.  
  
 **표시 ID**  
 프로파일링 표시의 고유한 ID입니다.  
  
 **표시 이름**  
 이벤트의 이름입니다.  
  
 **타임스탬프**  
 프로파일링  시작부터 이벤트가 기록되는 시간까지의 시간입니다.  
  
 Windows 성능 카운터 데이터  
 Windows 성능 카운터 데이터가 수집되는 경우 해당 카운터 이름이 있는 열에 값이 표시됩니다.  
  
## 참고 항목  
 [프로파일링 도구 보고서 개요](../profiling/performance-report-overview.md)   
 [\<PAVE\_OVER\> 방법: 프로파일링 표시 구성](../Topic/%3CPAVE_OVER%3E%20How%20to:%20Configure%20Profiling%20Marks.md)   
 [\<PAVE\_OVER\> 방법: 프로파일러 데이터 파일에 표시 삽입](../Topic/%3CPAVE_OVER%3E%20How%20to:%20Insert%20Marks%20in%20a%20Profiler%20Data%20File.md)   
 [방법: Windows 카운터 데이터 수집](../profiling/how-to-collect-windows-counter-data.md)   
 [&#91;NIB&#93; Data Collection Control Window](http://msdn.microsoft.com/ko-kr/98d740d8-459f-4605-bf04-fb17aafaaa8f)