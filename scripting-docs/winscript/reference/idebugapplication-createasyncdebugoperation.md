---
title: "IDebugApplication::CreateAsyncDebugOperation | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.CreateAsyncDebugOperation
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::CreateAsyncDebugOperation"
ms.assetid: bc32b101-6364-4498-8458-bd5f3ab5ad94
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::CreateAsyncDebugOperation
주어진된 동기 디버그 작업 비동기 액세스를 제공합니다.  
  
## 구문  
  
```  
HRESULT CreateAsyncDebugOperation(  
   IDebugSyncOperation*    psdo,  
   IDebugAsyncOperation**  ppado  
);  
```  
  
#### 매개 변수  
 `psdo`  
 \[in\] 동기 디버그 작업 개체입니다.  
  
 `ppado`  
 \[out\] 비동기 디버그 작업 개체입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 언어 엔진을 스레드와 디버거를 명시적으로 동기화 하지 않고 비동기적으로 식을 계산할 수 있습니다.  자세한 내용은 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md) 및 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)을 참조하십시오.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugSyncOperation 인터페이스](../../winscript/reference/idebugsyncoperation-interface.md)   
 [IDebugAsyncOperation 인터페이스](../../winscript/reference/idebugasyncoperation-interface.md)