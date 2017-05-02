---
title: "ICanHandleException::CanHandleException | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: ICanHandleException.CanHandleException
apilocation: scrobj.dll
helpviewer_keywords: 
  - "ICanHandleException::CanHandleException"
ms.assetid: 0fc703bf-9518-487e-af20-00e073b640f1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# ICanHandleException::CanHandleException
스크립트 엔진의 호출자는 지정 된 예외를 처리할 수 있는지 확인 합니다.  
  
## 구문  
  
```  
HRESULT CanHandleException(  
   EXCEPINFO*  pExcepInfo,  
   VARIANT*    pvar  
);  
```  
  
#### 매개 변수  
 `pExcepInfo`  
 \[in\] 포인터는 `EXCEPINFO` 예외 처리기가 있으면 보고 정보가 포함 된 구조입니다.  
  
 `pvar`  
 \[in\] 연결 된 예외를 throw 하는 값과 같은 값을 `throw` 문.  이 매개 변수는 `NULL`일 수 있습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|호출자에 게 예외를 처리할 수 있습니다.|  
|`E_FAIL`|호출자에 게 예외를 처리할 수 없습니다.|  
  
## 설명  
 호출 하는 경우 `IDispatchEx::InvokeEx`, 또는 유사한 방법으로 결과 예외가 호출자를 지 원하는 스크립트의 호출자 체인에 대 한 스크립트 엔진 검사는 `ICanHandleException` 인터페이스 및 예외를 처리할 수 있음을 나타냅니다.  호출자는 예외를 처리할 수 있으면 스크립트 엔진을 중지 합니다.  
  
## 참고 항목  
 [ICanHandleException 인터페이스](../../winscript/reference/icanhandleexception-interface.md)   
 [IDispatchEx::InvokeEx](../../winscript/reference/idispatchex-invokeex.md)