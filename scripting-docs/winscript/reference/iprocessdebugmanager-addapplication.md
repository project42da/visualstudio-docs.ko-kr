---
title: "IProcessDebugManager::AddApplication | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IProcessDebugManager.AddApplication
apilocation: pdm.dll
helpviewer_keywords: 
  - "IProcessDebugManager::AddApplication"
ms.assetid: 73828299-11eb-4c58-ad70-f80f2d0eede8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IProcessDebugManager::AddApplication
실행 중인 응용 프로그램의 응용 프로그램 컴퓨터 디버그 관리자 목록에 추가 합니다.  
  
## 구문  
  
```  
HRESULT AddApplication(  
   IDebugApplication*  pda,  
   DWORD*              pdwAppCookie  
);  
```  
  
#### 매개 변수  
 `pda`  
 \[in\] 실행 중인 응용 프로그램 목록에 추가 하려면 디버그 응용 프로그램입니다.  
  
 `pdwAppCookie`  
 \[out\] 컴퓨터 디버그 관리자에서 응용 프로그램을 제거 하는 데 사용 되는 쿠키입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 응용 프로그램을 실행 하는 추가 컴퓨터 디버그 관리자에서 응용 프로그램 목록입니다.  
  
## 참고 항목  
 [IProcessDebugManager 인터페이스](../../winscript/reference/iprocessdebugmanager-interface.md)   
 [IProcessDebugManager::RemoveApplication](../../winscript/reference/iprocessdebugmanager-removeapplication.md)