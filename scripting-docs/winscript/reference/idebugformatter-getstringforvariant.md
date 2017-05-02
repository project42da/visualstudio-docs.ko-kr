---
title: "IDebugFormatter::GetStringForVariant | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugFormatter.GetStringForVariant
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugFormatter::GetStringForVariant"
ms.assetid: 95189d03-1126-433e-8513-659107b3df16
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugFormatter::GetStringForVariant
지정 된 VARIANT 값을 나타내는 string을 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetStringForVariant(  
   VARIANT*  pvar,  
   ULONG     nRadix,  
   BSTR*     pbstrValue  
);  
```  
  
#### 매개 변수  
 `pvar`  
 \[in\] 문자열 형식으로 나타내는 VARIANT입니다.  
  
 `nRadix`  
 \[in\] 숫자 값에 사용할 기 수입니다.  
  
 `pbstrValue`  
 \[out\] 문자열을 나타내는 `pvar`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 이렇게 지정 된 variant 값을 나타내는 string을 반환 합니다.  
  
## 참고 항목  
 [IDebugFormatter 인터페이스](../../winscript/reference/idebugformatter-interface.md)