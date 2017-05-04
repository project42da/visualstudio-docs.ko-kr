---
title: "ISimpleConnectionPoint::Advise | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ISimpleConnectionPoint.Advise
apilocation: pdm.dll
helpviewer_keywords: 
  - "ISimpleConnectionPoint::Advise"
ms.assetid: 59ded60d-b938-4110-aca3-e69ba234ca9a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ISimpleConnectionPoint::Advise
간단한 연결 지점 개체와 클라이언트 싱크 간에 연결을 설정합니다.  
  
## 구문  
  
```  
HRESULT Advise(  
   IDispatch*  pdisp,  
   DWORD*      pdwCookie  
);  
```  
  
#### 매개 변수  
 `pdisp`  
 \[in\] 포인터는 `IDispatch` 인터페이스 클라이언트 싱크 권고의.  클라이언트의 싱크입니다 단순 연결 지점에서 나가는 호출을 받습니다.  
  
 `pdwCookie`  
 \[out\] 이 연결을 고유 하 게 식별 하는 반환 된 토큰에 대 한 포인터입니다.  호출자가이 토큰 나중에 전달 하 여 연결을 삭제 하는 `ISimpleConnectionPoint::Unadvise` 메서드.  연결이 설정 된 경우이 값은 0입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 단순 연결 지점 개체와 클라이언트 싱크 간에 연결을 설정합니다.  
  
## 참고 항목  
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)   
 [ISimpleConnectionPoint::Unadvise](../../winscript/reference/isimpleconnectionpoint-unadvise.md)