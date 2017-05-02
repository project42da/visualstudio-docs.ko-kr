---
title: "IDispError::GetHresult | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispError.GetHresult
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDispError::GetHresult"
ms.assetid: a14d566e-473f-497b-a2f9-85331433e6c9
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispError::GetHresult
검색에서 오류 코드는 `IDispError` 개체입니다.  
  
## 구문  
  
```  
HRESULT GetHresult(  
   HRESULT*  phr  
);  
```  
  
#### 매개 변수  
 `phr`  
 \[out\] 오류 코드를 지정합니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 오류 코드에서이 메서드는 검색 된 `IDispError` 개체입니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않은 경우  
  
## 참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)