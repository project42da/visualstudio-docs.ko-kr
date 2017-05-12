---
title: "IJsDebugDataTarget::AllocateVirtualMemory 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.AllocateVirtualMemory
apilocation: jscript9diag.dll
ms.assetid: 1d3a77b0-c1de-4a0c-a759-3e0c68fd96dd
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::AllocateVirtualMemory 메서드
대상 프로세스의 가상 주소 공간 내의 메모리 영역 예약 및\/또는 커밋  
  
## 구문  
  
```  
HRESULT AllocateVirtualMemory(  
   UINT64 address,  
   DWORD size,  
   DWORD allocationType,  
   DWORD pageProtection,  
   UINT64 *pAllocatedAddress  
);  
```  
  
#### 매개 변수  
 `address`  
 \[in\] 메모리를 커밋하거나 예약해야 하는 대상 프로세스 내의 주소입니다.  이 값은 일반적으로 0이며, 시스템이 주소를 선택합니다.  
  
 `size`  
 \[in\] 할당할 메모리 영역의 크기\(바이트\)입니다.  시스템이 자동으로 다음 페이지 경계로 올림합니다.  
  
 `allocationType`  
 \[in\] 수행하려는 할당 유형을 나타냅니다.  일반적으로 할당을 한 단계로 예약 및 커밋하는 MEM\_COMMIT &#124; MEM\_RESERVE\(0x3000\)입니다.  
  
 `pageProtection`  
 \[in\] 할당할 페이지 영역에 대한 메모리 보호입니다.  페이지가 커밋되는 경우 메모리 보호 상수\(예: PAGE\_READWRITE, PAGE\_EXECUTE\) 중 하나를 지정할 수 있습니다.  
  
 `pAllocatedAddress`  
 \[out\] 할당된 페이지 영역의 기준 주소입니다.  
  
## 반환 값  
  
## 설명  
 함수는 MEM\_RESET를 사용하지 않으면 할당된 메모리를 0으로 초기화합니다.  추가 정보는 VirtualAlloc Win32 API를 참조하십시오.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)