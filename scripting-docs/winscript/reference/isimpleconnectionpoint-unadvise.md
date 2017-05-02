---
title: "ISimpleConnectionPoint::Unadvise | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ISimpleConnectionPoint.Unadvise
apilocation: pdm.dll
helpviewer_keywords: 
  - "ISimpleConnectionPoint::Unadvise"
ms.assetid: eae06a58-ed42-4839-aad4-14420b15343f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ISimpleConnectionPoint::Unadvise
`ISimpleConnectionPoint::Advise`를 통해 이전에 설치된 권장된 연결을 종료합니다.  
  
## 구문  
  
```  
HRESULT Unadvise(  
   DWORD  dwCookie  
);  
```  
  
#### 매개 변수  
 `dwCookie`  
 \[in\] 토큰의 연결에서 반환 된 종료 `ISimpleConnectionPoint::Advise`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 권장 되는 연결 종료 되 면 연결 지점 호출을 `Release` 에 연결 되어 있는 동안 저장 된 포인터 메서드는 `ISimpleConnectionPoint::Advise` 메서드.  반대로 호출의 `AddRef` 동안 수행 된는 `ISimpleConnectionPoint::Advise` 때 연결점 호출의 advise 싱크 `QueryInterface`.  
  
## 참고 항목  
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)