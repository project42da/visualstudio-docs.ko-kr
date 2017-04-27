---
title: "테스트 영역 6: 삭제 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 [Visual Studio SDK], 항목 삭제"
  - "소스 제어 플러그 인, 항목 삭제"
ms.assetid: 6f2e872c-5ba2-4303-9f50-a90cef9a6225
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 테스트 영역 6: 삭제
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 소스 제어 플러그 인 테스트 영역 삭제 작업에 설명합니다.  
  
 소스 제어 작업을 삭제로 응답  **솔루션 탐색기**.  
  
 다음 삭제할 수 있는 항목의 목록입니다.  
  
-   Files  
  
-   폴더  
  
-   프로젝트  
  
 프로젝트 형식에 따라 옵션을 있을 수 있습니다  **제거** \(디스크에 있는 파일을 그대로 둡니다.\) 프로젝트 또는  **삭제** 프로젝트 \(디스크에 있는 파일을 제거\).  프로젝트 또는 항목에서 둘 중 어느 쪽을 제거  **솔루션 탐색기**.  
  
## 예상 되는 동작  
 Delete 테스트 영역에서 테스트 사례에 대 한 예상 되는 동작은 다음과 같습니다.  
  
-   삭제 된 항목 내에 표시 됩니다 더 이상  **솔루션 탐색기**.  
  
-   삭제 된 프로젝트 또는 항목의 부모 \(가능한 경우 사용 하 여 프롬프트.\) 필요에 따라 체크 아웃  
  
-   체크 아웃을 삭제 또는 추가 후에 나타나지 않는 있는  **보류 중인 체크 인** 창입니다.  
  
-   항목이 소스 제어 저장소에서 삭제 후에 있으며 수동으로 제거 해야 합니다.  
  
|동작|테스트 단계|예상된 결과 확인 하려면|  
|--------|------------|-------------------|  
|클라이언트 프로젝트를 삭제 합니다.|1.  클라이언트 프로젝트를 만듭니다.<br />2.  소스 제어에 솔루션을 추가 합니다.<br />3.  전체 프로젝트를 솔루션에서 제거|일반적인 예상 되는 동작입니다.|  
|빈 파일을 삭제 합니다.|1.  클라이언트 프로젝트를 만듭니다.<br />2.  0 바이트 파일을 프로젝트에 추가 합니다.<br />3.  소스 제어에 솔루션을 추가 합니다.<br />4.  파일을 선택 하 고 삭제 합니다.|일반적인 예상 되는 동작입니다.|  
|하나 이상의 파일과 폴더를 삭제 합니다.|1.  단일 프로젝트 솔루션을 만듭니다.<br />2.  폴더를 추가 합니다.<br />3.  파일을 폴더에 추가 합니다.<br />4.  소스 제어에 솔루션을 추가 합니다.<br />5.  프롬프트가 표시 되지 않도록 하려면 프로젝트를 체크 아웃 합니다.<br />6.  폴더를 삭제 합니다.|일반적인 예상 되는 동작입니다.|  
|파일 시스템 웹 프로젝트 삭제|1.  파일 시스템 웹 프로젝트 \(사용할 UNC 경로 지정 하려면 찾아보기 단추\)을 만듭니다.<br />2.  소스 제어에 솔루션을 추가 합니다.<br />3.  전체 프로젝트를 솔루션에서 제거 합니다.<br />4.  로컬 웹 프로젝트에 대해 1\-3 단계를 반복 합니다. \(서로 다른 경로 통해 코드를 실행 하지만 같은 외부 인터페이스와 동작\).|일반적인 예상 되는 동작입니다.|  
|파일 시스템 웹 프로젝트에서 파일을 삭제 합니다.|1.  파일 시스템 웹 프로젝트를 만듭니다.<br />2.  소스 제어에 솔루션을 추가 합니다.<br />3.  프로젝트에서 파일을 삭제 합니다.<br />4.  로컬 웹 프로젝트에 대해 1\-3 단계를 반복 합니다. \(서로 다른 경로 통해 코드를 실행 하지만 같은 외부 인터페이스와 동작\).|일반적인 예상 되는 동작입니다.|  
  
## 참고 항목  
 [소스 제어 플러그 인에 대 한 테스트 가이드](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)