---
title: "IJsDebugDataTarget::ReadMemory 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.ReadMemory
apilocation: jscript9diag.dll
ms.assetid: 664e0f7d-2007-45f4-b993-36fe8b1944e5
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::ReadMemory 메서드
대상 프로세스의 메모리를 읽습니다.  
  
## 구문  
  
```  
HRESULT ReadMemory(  
   UINT64 address,  
   JsDebugReadMemoryFlags flags,  
   BYTE *pBuffer,  
   DWORD size,  
   DWORD *pBytesRead  
);  
```  
  
#### 매개 변수  
 `address`  
 \[in\] 대상 프로세스의 메모리를 읽을 기준 주소입니다.  
  
 `flags`  
 \[in\] ReadMemory 동작을 제어하는 플래그입니다.  
  
 `pBuffer`  
 \[out\] 대상 프로세스의 주소 공간에서 콘텐츠를 받는 버퍼입니다.  실패한 경우,이 버퍼의 내용은 지정되지 않습니다.  
  
 `size`  
 \[in\] 프로세스에서 읽을 바이트 수입니다.  
  
 `pBytesRead`  
 \[out\] 대상 프로세스에서 읽은 바이트 수를 나타냅니다.  JsDebugAllowPartialRead가 분명한 경우 성공 시 이 값은 항상 입력 크기와 정황하게 일치합니다.  JsDebugAllowPartialRead가 지정된 경우 성공 시 이 값은 0보다 큽니다.  
  
## 반환 값  
  
## 설명  
 성공과 실패 코드에서 반환하는 S\_OK는 오류에 대해 사용됩니다.  주소가 유효하지 않으면 E\_JsDEBUG\_INVALID\_MEMORY\_ADDRESS를 반환합니다.  자세한 내용은 JsDebugAllowPartialRead를 참조하십시오.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)