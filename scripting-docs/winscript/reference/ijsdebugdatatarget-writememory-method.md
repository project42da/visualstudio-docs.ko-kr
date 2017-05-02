---
title: "IJsDebugDataTarget::WriteMemory 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.WriteMemory
apilocation: jscript9diag.dll
ms.assetid: 0d3c04c3-9ef8-4842-a145-3d29bca75062
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::WriteMemory 메서드
대상 프로세스의 메모리를 읽습니다.  
  
## 구문  
  
```  
HRESULT WriteMemory(  
   UINT64 address,  
   const BYTE *pMemory,  
   DWORD size  
);  
```  
  
#### 매개 변수  
 `address`  
 \[in\] 대상 프로세스의 메모리를 쓸 기준 주소입니다.  
  
 `pMemory`  
 \[in\] 지정된 프로세스의 주소 공간에 쓸 데이터입니다.  
  
 `size`  
 \[in\] 프로세스에 쓸 바이트 수입니다.  
  
## 반환 값  
  
## 설명  
 데이터 전송이 발생하기 전에 시스템은 기준 주소에 있는 모든 데이터와 지정된 크기의 메모리에 쓰기 액세스할 수 있는지 확인하고 액세스할 수 없는 경우 함수는 E\_JsDEBUG\_INVALID\_MEMORY\_ADDRESS 오류를 발생시킵니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)