---
title: "오류: 원격 컴퓨터에서 DCOM 통신을 시작하지 못했습니다. | Microsoft Docs"
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
  - "vs.debug.error.unmarshal_callback_failed"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: bbba0766-2502-4ef1-a75d-bf1f0db39e37
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: 원격 컴퓨터에서 DCOM 통신을 시작하지 못했습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

원격 컴퓨터에서 로컬 컴퓨터와 통신을 시도하는 동안 DCOM 오류가 발생했습니다.  Visual Studio에서 실행되는 컴퓨터는  
  
 로컬 컴퓨터입니다.  여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.  
  
-   로컬 컴퓨터에서 방화벽을 사용하고 있습니다.  
  
-   원격 컴퓨터에서 로컬 컴퓨터에 대한 Windows 인증이 작동하지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  로컬 컴퓨터에서 Windows 방화벽을 사용하는 경우에 로컬 디버깅을 위해 방화벽을 구성하는 방법에 대한 지침은 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)을 참조하십시오.  
  
2.  원격 서버에서 로컬 컴퓨터의 파일 공유 위치를 열어 Windows 인증을 테스트합니다.  
  
3.  Windows 인증을 복원하려면 두 컴퓨터를 모두 다시 부팅합니다.  로컬 컴퓨터와 원격 컴퓨터에서 이벤트 로그를 검사하여 Kerberos 오류가 있는지 확인하고 알려진 문제가 있는지 도메인 관리자에게 문의합니다.  
  
## 참고 항목  
 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)