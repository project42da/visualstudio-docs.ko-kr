---
title: "오류: DCOM 통신을 초기화할 수 없습니다. | Microsoft Docs"
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
  - "vs.debug.error.unmarshal_server_failed"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 2a7b27e6-2526-4f32-bc4d-eaee447f24ec
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: DCOM 통신을 초기화할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

로컬 컴퓨터에서 원격 컴퓨터와 통신을 시도하는 동안 DCOM 오류가 발생했습니다.  원격 서버의 방화벽 때문이거나 원격 컴퓨터의 Windows 인증이 손상되었기 때문일 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   원격 컴퓨터에서 Windows 방화벽을 사용하는 경우에 로컬 디버깅을 위해 방화벽을 구성하는 방법에 대한 지침은 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)을 참조하십시오.  
  
-   Windows 인증을 복원하려면 두 컴퓨터를 모두 다시 부팅합니다.  로컬 컴퓨터와 원격 컴퓨터에서 이벤트 로그를 검사하여 Kerberos 오류가 있는지 확인하고 알려진 문제가 있는지 도메인 관리자에게 문의합니다.  
  
## 참고 항목  
 [원격 디버깅](../debugger/remote-debugging.md)