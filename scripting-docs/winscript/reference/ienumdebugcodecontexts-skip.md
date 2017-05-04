---
title: "IEnumDebugCodeContexts::Skip | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IEnumDebugCodeContexts.Skip
apilocation: jscript.dll
helpviewer_keywords: 
  - "IEnumDebugCodeContexts::Skip"
ms.assetid: ba917f57-f7a9-419f-96d6-8f4378b12c57
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IEnumDebugCodeContexts::Skip
열거형 시퀀스에서 지정된 수의 세그먼트를 건너뜁니다.  
  
## 구문  
  
```  
HRESULT Skip(  
   ULONG  celt  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 건너뛸 열거 시퀀스 세그먼트의 수입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 세그먼트는 열거 시퀀스에서 지정한 개수의 건너뜁니다.  
  
## 참고 항목  
 [IEnumDebugCodeContexts 인터페이스](../../winscript/reference/ienumdebugcodecontexts-interface.md)