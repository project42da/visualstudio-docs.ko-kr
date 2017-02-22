---
title: "줄 뷰 - 프로파일러 샘플링 데이터 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "줄 뷰"
ms.assetid: 46497249-c797-42c5-a02c-3e4bb3b4ee60
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 줄 뷰 - 프로파일러 샘플링 데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

샘플링 데이터의 줄 뷰에는 프로파일링 실행 시 샘플이 수집될 때 실행되고 있던 문에 대한 성능 데이터가 표시됩니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
 소스 파일에서는 하나의 문이 소스 파일의 여러 줄에 걸쳐 있거나 한 줄에 여러 문이 포함될 수 있습니다.  문은 다음에 의해 식별됩니다.  
  
-   함수 문이 포함된 소스 파일  
  
-   문이 포함된 함수  
  
-   문이 시작되는 소스 줄  
  
-   문이 시작되는 소스 줄의 문자  
  
-   문이 끝나는 소스 줄  
  
-   문이 끝나는 소스 줄의 문자  
  
 줄 이름 열에서는 식별자 데이터의 정렬 가능한 연결을 제공합니다.  
  
 정의에 따라 문은 다른 함수를 호출하지 않습니다.  따라서 전용 값만 표시됩니다.  
  
|열|설명|  
|-------|--------|  
|**프로세스 ID**|프로파일링 실행의 PID\(프로세스 ID\)입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**모듈 이름**|함수 줄이 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수 줄이 포함된 모듈의 경로입니다.|  
|**소스 파일**|함수 줄이 포함된 소스 파일입니다.|  
|**함수 이름**|함수의 이름.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**함수 주소**|함수의 시작 주소입니다.|  
|**소스 줄 시작**|소스 파일에서 이 샘플이 수집된 시작 줄 번호입니다.|  
|**소스 줄 끝**|소스 파일에서 이 샘플이 수집된 끝 줄 번호입니다.|  
|**소스 문자 시작**|소스 파일 줄에서 이 샘플이 수집된 시작 문자의 오프셋입니다.|  
|**소스 문자 끝**|소스 파일 줄에서 이 샘플이 수집된 끝 문자의 오프셋입니다.|  
|**줄 이름**|`Source File` **;\[** `Line Number Start` **,** `Character Start` **\]\-\>;\[** `Line Number End`,`Character End`**\]** 구문으로 프로파일러에서 생성한 줄 식별자입니다.|  
|**제외 샘플**|함수 줄이 실행될 때 수집된 총 샘플 수입니다.|  
|**전용 샘플 비율\(%\)**|프로파일링 실행 시 전체 샘플 중 해당 함수 줄이 실행될 때 수집된 샘플의 백분율입니다.|  
  
## 참고 항목  
 [줄 뷰 \- 샘플링](../profiling/lines-view-dotnet-memory-sampling-data.md)