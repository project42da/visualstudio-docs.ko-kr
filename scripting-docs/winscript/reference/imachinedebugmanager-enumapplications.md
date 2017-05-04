---
title: "IMachineDebugManager::EnumApplications | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IMachineDebugManager.EnumApplications
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IMachineDebugManager::EnumApplications"
ms.assetid: 5d833db4-fd9b-4e61-bebb-130faede5a77
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IMachineDebugManager::EnumApplications
현재 실행 중인 응용 프로그램 목록에 대 한 열거자를 반환 합니다.  
  
## 구문  
  
```  
HRESULT EnumApplications(  
   IEnumRemoteDebugApplications**  ppeda  
);  
```  
  
#### 매개 변수  
 `ppeda`  
 \[out\] 현재 실행 중인 응용 프로그램 목록을 포함 하는 열거자입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 열거자의 현재 실행 중인 응용 프로그램 목록 반환 합니다.  IDE 디버거에서이 메서드를 사용 하 여 표시 하 고 디버깅 목적으로 응용 프로그램을 연결 합니다.  
  
## 참고 항목  
 [IMachineDebugManager 인터페이스](../../winscript/reference/imachinedebugmanager-interface.md)