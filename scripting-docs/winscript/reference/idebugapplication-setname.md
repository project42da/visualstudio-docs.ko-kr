---
title: "IDebugApplication::SetName | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.SetName
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::SetName"
ms.assetid: 7b0ddc58-6f20-4ce3-9bdf-81a6c1d64256
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::SetName
응용 프로그램 이름을 설정합니다.  
  
## 구문  
  
```  
HRESULT SetName(  
   LPCOLESTR  pstrName  
);  
```  
  
#### 매개 변수  
 `pstrName`  
 \[in\] 응용 프로그램의 이름입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드에 제공 된 이름이 후속 호출에 반환 되는 `IRemoteDebugApplication::GetName` 메서드.  
  
 이 메서드를 호출 하기 전에 호출 해야는 `IProcessDebugManager::AddApplication` 메서드.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IProcessDebugManager::AddApplication](../../winscript/reference/iprocessdebugmanager-addapplication.md)