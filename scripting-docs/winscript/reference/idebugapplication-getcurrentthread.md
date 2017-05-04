---
title: "IDebugApplication::GetCurrentThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.GetCurrentThread
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::GetCurrentThread"
ms.assetid: 15128e77-6fc6-42a2-8c04-20e22ef03f29
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::GetCurrentThread
현재 실행 중인 스레드에 스레드를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetCurrentThread(  
   IDebugApplicationThread**  pat  
);  
```  
  
#### 매개 변수  
 `pat`  
 \[out\] 현재 실행 중인 스레드와 연관 된 스레드입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 현재 실행 중인 스레드와 연관 된 스레드를 반환 합니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)