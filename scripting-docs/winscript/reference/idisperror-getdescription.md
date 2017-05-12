---
title: "IDispError::GetDescription | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispError.GetDescription
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDispError::GetDescription"
ms.assetid: 04deaea6-0265-4e34-952e-634edba0e923
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispError::GetDescription
오류를 설명 하는 텍스트를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetDescription(  
   BSTR*  pbstrDescription  
);  
```  
  
#### 매개 변수  
 `pbstrDescription`  
 \[out\] 오류에 대 한 간략 한 설명을 포함 하는 문자열입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 전달 된 로케일 식별자 \(LCID\)에 의해 지정 된 언어에서의 텍스트가 반환 됩니다. `IDispatchEx::InvokeEx` 메서드의 오류가 발생 했습니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않은 경우  
  
## 참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)   
 [IDispatchEx::InvokeEx](../../winscript/reference/idispatchex-invokeex.md)