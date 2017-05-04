---
title: "IJsDebugDataTarget::FreeVirtualMemory 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.FreeVirtualMemory
apilocation: jscript9diag.dll
ms.assetid: ea54bad3-9ae3-436b-974d-70fc7fffefd6
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::FreeVirtualMemory 메서드
대상 프로세스의 가상 주소 공간 내의 메모리 영역 해제 및\/또는 커밋 해제  
  
## 구문  
  
```  
HRESULT FreeVirtualMemory(  
   UINT64 address,  
   DWORD size,  
   DWORD freeType  
);  
```  
  
#### 매개 변수  
 `address`  
 \[in\] 메모리를 해제해야 하는 대상 프로세스 내의 주소입니다.  
  
 `size`  
 \[in\] 커밋 해제할 바이트 수입니다.  메모리 영역을 해제하려면 이 값이 0이어야 합니다.  
  
 `freeType`  
 \[in\] 수행하려는 사용 가능한 작업 유형을 나타냅니다.  일반적으로 페이지의 지정된 영역을 릴리스하는 MEM\_RELEASE\(0x8000\)입니다.  작업이 끝나면 페이지는 비어 있는 상태가 됩니다.  변수를 해제하지 않고 MEM\_DECOMMIT\(0x4000\)를 페이지 커밋 해제 대신 사용할 수 있습니다.  
  
## 반환 값  
  
## 설명  
 추가 정보는 VirtualFree Win32 API를 참조하십시오.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)