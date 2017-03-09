---
title: "오류: 컴퓨터 &lt;name&gt;에 연결할 수 없습니다. 컴퓨터를 네트워크에서 찾을 수 없습니다. | Microsoft Docs"
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
  - "vs.debug.remote.dcom_disabled"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "DCOM, 연결 실패 오류"
ms.assetid: b584b5db-ef52-45ed-8561-1314da3cc5b8
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: 컴퓨터 &lt;name&gt;에 연결할 수 없습니다. 컴퓨터를 네트워크에서 찾을 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 오류는 다음과 같은 경우에 발생합니다.  
  
-   원격 컴퓨터에 대한 연결이 끊어진 경우  
  
-   원격 컴퓨터의 사용자 계정이 비활성화된 경우  
  
-   원격 컴퓨터의 암호가 만료된 경우  
  
### 이 동작을 해결하려면  
  
-   로컬 컴퓨터와 원격 컴퓨터가 동일한 네트워크에 있는지 확인합니다.  이를 확인하려면 Microsoft Windows 탐색기\(또는 파일 탐색기\)를 사용하여 원격 컴퓨터에 액세스해 봅니다.  
  
     — 및 —  
  
-   원격 컴퓨터에 연결하는 데 사용 중인 사용자 계정이 활성화되어 있는지 확인합니다.  
  
     — 및 —  
  
-   원격 컴퓨터에 연결하는 데 사용 중인 암호가 유효하고 만료되지 않았는지 확인합니다.  
  
## 참고 항목  
 [장치에서 원격 도구 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)   
 [디버그 설정 및 준비](../debugger/debugger-settings-and-preparation.md)