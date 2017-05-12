---
title: "IJsDebugFrame::GetStackRange 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugFrame.GetStackRange
apilocation: jscript9diag.dll
ms.assetid: a6d1d8be-efc0-442d-9756-1959c8f102bd
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugFrame::GetStackRange 메서드
논리 JavaScript 스택 프레임의 절대 주소 범위를 반환합니다.  
  
## 구문  
  
```  
HRESULT GetStackRange(  
   UINT64 *pStart,  
   UINT64 *pEnd  
);  
```  
  
#### 매개 변수  
 `pStart`  
 \[out\] 프레임의 최하위 스택 포인터입니다.  
  
 `pEnd`  
 \[out\] 프레임의 최상위 스택 포인터입니다.  
  
## 반환 값  
  
## 설명  
 이 메서드는 여러 런타임에서 수집된 인터리브된 스택 추적을 하나로 결합하는 데 유용합니다.  시작, 끝 스택 포인터에는 여러 물리적 컴퓨터 스택 프레임\(해석된 JavaScript 런타임 프레임의 경우\)이 포함될 수 있습니다. 스택이 높은 주소에서 낮은 주소로 증가하므로 시작 \> 종료입니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugFrame 인터페이스](../../winscript/reference/ijsdebugframe-interface.md)