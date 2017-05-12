---
title: "IJsDebugDataTarget::ReadNullTerminatedString 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.ReadNullTerminatedString
apilocation: jscript9diag.dll
ms.assetid: 64683b39-6fc2-40c4-82ae-2a6f58d392d5
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::ReadNullTerminatedString 메서드
대상에서 지정한 문자 수를 읽습니다.  
  
## 구문  
  
```  
HRESULT ReadNullTerminatedString(  
   UINT64 address,  
   UINT16 characterSize,  
   UINT32 maxCharacters,  
   BSTR *pString  
);  
```  
  
#### 매개 변수  
 `address`  
 \[in\] 읽어올 주소입니다.  
  
 `characterSize`  
 \[in\] 문자열에 있는 각 문자의 크기입니다.  
  
 `maxCharacters`  
 \[in\] 읽을 최대 문자 수입니다. maxCharacters는 적절해야 합니다.  128MB 이상의 메모리에 대한 모든 요청은 실패합니다.  문자열이 MaxCharacters 보다 큰 경우 결과 문자열이 maxCharacters 이후로 잘립니다.  
  
 `pString`  
 \[out\] 대상에서 읽히는 BSTR입니다.  
  
## 반환 값  
  
## 설명  
 잘리면 S\_FALSE를 반환합니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)