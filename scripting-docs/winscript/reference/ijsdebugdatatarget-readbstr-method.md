---
title: "IJsDebugDataTarget::ReadBSTR 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.ReadBSTR
apilocation: jscript9diag.dll
ms.assetid: 4b571db7-04b9-42a0-9a3e-310ac9d0e659
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::ReadBSTR 메서드
디버그 대상에서 읽히는 BSTR을 읽습니다.  
  
## 구문  
  
```  
HRESULT ReadBSTR(  
   UINT64 address,  
   BSTR *pString  
);  
```  
  
#### 매개 변수  
 `address`  
 \[in\] 읽어올 주소입니다.  
  
 `pString`  
 \[out\] 디버그 대상에서 읽히는 BSTR입니다.  
  
## 반환 값  
  
## 설명  
 주소가 유효하지 않으면 E\_JsDEBUG\_INVALID\_MEMORY\_ADDRESS를 반환합니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)