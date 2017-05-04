---
title: "IActiveScriptProfilerCallback3::SetWebWorkerId 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 47744746-1276-441e-ab60-2a78f550e8e2
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IActiveScriptProfilerCallback3::SetWebWorkerId 메서드
이 대 한 프로 파일링 세션을 사용 하는 작업자 ID에 대 한 프로파일러를 알립니다.  다음 함수는 페이지의 컨텍스트 내에서 실행 되지 않는 경우이 메서드는 호출 되지 않습니다.  값은 `webWorkerId` 1부터 시작 하는 모든 작업자를 1 씩 증가 합니다.  ID 값에는 세션 이후에 불안정 한 작업 자가 만들어진 순서에 아닙니다.  
  
## 구문  
  
```  
HRESULT SetWebWorkerId([in] DWORD webWorkerId);  
  
```  
  
#### 매개 변수  
 `webWorkerId`  
 웹 작업자 id입니다.  
  
## 반환 값  
 이 메서드의 반환 값은 스크립트 엔진에 의해 무시 됩니다.