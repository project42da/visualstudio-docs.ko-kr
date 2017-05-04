---
title: "IDispError::GetNext | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispError.GetNext
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IDispError::GetNext"
ms.assetid: 3e5267f8-ba62-41c3-bd3e-eced2ad85e8e
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispError::GetNext
다음 검색 `IDispError` 개체입니다.  
  
## 구문  
  
```  
HRESULT GetNext(  
   IDispError**  ppde  
);  
```  
  
#### 매개 변수  
 `ppde`  
 \[out\] 그런 다음 지정 `IDispError` 개체입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 다음 검색 `IDispError` 개체입니다.  마지막 경우 `IDispError` 개체에서이 메서드는 NULL을 반환 합니다.  
  
> [!NOTE]
>  이 메서드가 구현되지 않은 경우  
  
## 참고 항목  
 [IDispError 인터페이스](../../winscript/reference/idisperror-interface.md)