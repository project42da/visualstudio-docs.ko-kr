---
title: "방법: 호스팅 프로세스 비활성화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "호스팅 프로세스, 비활성화"
  - "vshost.exe, 호스팅 프로세스 비활성화"
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
caps.latest.revision: 10
caps.handback.revision: 10
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: 호스팅 프로세스 비활성화
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

특정 API에 대한 호출은 호스팅 프로세스가 활성화될 때 영향을 받을 수 있습니다.  이러한 경우 올바른 결과를 반환하도록 호스팅 프로세스를 비활성화해야 합니다.  
  
### 호스팅 프로세스를 비활성화하려면  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 실행 가능한 프로젝트 열기  실행 파일 \(예: 클래스 라이브러리 또는 서비스 프로젝트\)을 생성하지 않는 프로젝트에는 이 옵션이 없습니다.  
  
2.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  
  
3.  **디버그** 탭을 클릭합니다.  
  
4.  **Visual Studio 호스팅 프로세스 사용** 확인란의 선택을 취소합니다.  
  
 호스팅 프로세스가 비활성화되면 몇 개의 디버깅 기능을 사용할 수 없거나 성능이 저하됩니다.  자세한 내용은 [디버깅 및 호스팅 프로세스](../debugger/debugging-and-the-hosting-process.md)을 참조하십시오.  
  
 일반적으로 호스팅 프로세스가 비활성화되는 경우는 다음과 같습니다.  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 응용 프로그램 디버깅을 시작하는 데 필요한 시간이 증가하는 경우  
  
-   디자인 타임에 식 계산을 사용할 수 없는 경우  
  
-   부분 신뢰 디버깅을 사용할 수 없는 경우  
  
## 참고 항목  
 [디버깅 및 호스팅 프로세스](../debugger/debugging-and-the-hosting-process.md)   
 [호스팅 프로세스\(vshost.exe\)](../ide/hosting-process-vshost-exe.md)   
 [Builds During Application Development](http://msdn.microsoft.com/ko-kr/c9497d62-3b7b-4449-88e8-cf27acc9efe6)