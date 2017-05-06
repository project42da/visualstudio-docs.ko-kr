---
title: "SetWefProcessId 메서드"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 404eec23-a67e-4f5b-b27d-86651f08be03
caps.latest.revision: 8
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 7
---
# SetWefProcessId 메서드
  웹 확장 프레임 워크 \(WEF\) 콘텐츠를 실행 하는 프로세스 id를 제공 합니다.  
  
## 구문  
  
```  
HRESULT SetWefProcessId(  
    [in] DWORD dwProcessId  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|*dwProcessId*|WEF 콘텐츠를 실행 하는 데 프로세스 식별자입니다.|  
  
## 반환 값  
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.  
  
## 설명  
 WEF 콘텐츠 프로세스를 만든 후 있지만 WEF 내용을 실행 하기 전에이 메서드를 호출 해야 합니다.  
  
 WEF 콘텐츠 프로세스에 디버거를 연결 하는 개발 환경에 필요한 경우 환경에이 메서드의 구현에서는이 작업을 수행 해야 합니다.  
  
  