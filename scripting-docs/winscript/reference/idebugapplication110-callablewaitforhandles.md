---
title: "IDebugApplication110::CallableWaitForHandles | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplication110::CallableWaitForHandles"
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IDebugApplication110::CallableWaitForHandles
대기 하면서 신호를 받도록 지정 된 핸들에 대 한 호출이이 스레드에 게시 하는 데 스레드 간.  디버거 스레드에서이 메서드를 호출 해야 합니다.  
  
> [!IMPORTANT]
>  [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
  
```  
  
#### 매개 변수  
 `handleCount`  
 대기 핸들의 수입니다.  
  
 `pHandles`  
 대기 핸들의 집합입니다.  
  
 `pIndex`  
 HRESULT 값 S\_OK로 인덱스 되 면 `pHandles` 핸들 신호를 했습니다.  
  
## 참고 항목  
 [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md)