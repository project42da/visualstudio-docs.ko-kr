---
title: "방법: 편집하며 계속하기 설정/해제 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "/INCREMENTAL 링커 옵션"
  - "코드 변경 내용 적용 명령"
  - "중단 모드, 코드 변경 내용 적용"
  - "코드 변경 내용, 중단 모드에서 적용"
  - "편집하며 계속하기, 코드 변경 내용 적용"
  - "편집하며 계속하기, 비활성화"
  - "편집하며 계속하기, 사용"
  - "이동 명령"
  - "INCREMENTAL 링커 옵션"
  - "단계 명령"
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 편집하며 계속하기 설정/해제
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집하며 계속하기는 디자인 타임에 **옵션** 대화 상자에서 사용하거나 사용하지 않도록 설정할 수 있습니다.  디버깅 중에는 이 설정을 변경할 수 없습니다.  
  
 편집하며 계속하기는 디버그 빌드에서만 작동합니다.  네이티브 C\+\+의 경우 편집하며 계속하기를 실행하려면 \/INCREMENTAL 옵션을 사용해야 합니다.  
  
## 절차  
  
#### 편집하며 계속하기를 사용하거나 사용하지 않도록 설정하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **옵션** 대화 상자에서 **디버깅** 노드를 열고 **편집하며 계속하기** 범주를 선택합니다.  
  
3.  이 기능을 사용하도록 설정하려면 **편집하며 계속하기 사용** 확인란을 선택합니다.  이 기능을 사용하지 않도록 설정하려면 이 확인란의 선택을 취소합니다.  
  
    > [!NOTE]
    >  IntelliTrace를 사용하도록 설정되어 있고 IntelliTrace 이벤트 및 호출 정보를 모두 수집하는 경우 편집하며 계속하기를 사용하지 않도록 설정됩니다.  자세한 내용은 [디버깅 정보를 수집하도록 IntelliTrace 구성](http://msdn.microsoft.com/ko-kr/7657ecab-e07e-4b1b-872d-f05d966be37e)을 참조하십시오.  
  
4.  **확인**을 클릭합니다.  
  
## 참고 항목  
 [편집하며 계속하기](../debugger/edit-and-continue.md)   
 [옵션 대화 상자, 디버깅, 편집하며 계속하기](../Topic/Edit%20and%20Continue,%20Debugging,%20Options%20Dialog%20Box.md)