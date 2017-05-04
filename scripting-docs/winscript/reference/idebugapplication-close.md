---
title: "IDebugApplication::Close | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.Close
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::Close"
ms.assetid: d19baa07-3f3b-47de-8185-5eb3e7ac8b46
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::Close
이 응용 프로그램에 대 한 모든 참조를 해제 하 고 비활성 상태가 됩니다.  
  
## 구문  
  
```  
HRESULT Close();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 일반적으로 응용 프로그램을 종료할 때 응용 프로그램의 소유자는이 메서드를 호출 합니다.  
  
 이 메서드로 인해 `IApplicationDebugger::onClose` 호출할 수 있습니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onClose](../../winscript/reference/iapplicationdebugger-onclose.md)