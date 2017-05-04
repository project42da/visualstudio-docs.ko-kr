---
title: "IRemoteDebugApplication::CreateInstanceAtApplication | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplication.CreateInstanceAtApplication
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplication::CreateInstanceAtApplication"
ms.assetid: d669ec80-2182-400d-87cc-7c1753315e5c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplication::CreateInstanceAtApplication
개체 만들기 프로세스에서 응용 프로그램 코드에 의해 허용 된\-out\-of\-process 응용 프로그램.  
  
## 구문  
  
```  
HRESULT CreateInstanceAtApplication(  
   REFCLSID    rclsid,  
   IUnknown*   pUnkOuter,  
   DWORD       dwClsContext,  
   REFIID      riid,  
   IUnknown**  ppvObject  
);  
```  
  
#### 매개 변수  
 `rclsid`  
 \[in\] 클래스 식별자 \(CLSID\) 개체를 만들려면  
  
 `pUnkOuter`  
 \[in\] 경우 `NULL`, 개체는 집합체의 일부로 생성 되지 합니다.  그렇지 않으면 `pUnkOuter` 는 집계 개체에 대 한 포인터는 `IUnknown` 인터페이스 \(제어는 `IUnknown`\).  
  
 `dwClsContext`  
 \[in\] 실행 코드를 실행 하는 컨텍스트.  열거형에서 수행 되는 값은 `CLSCTX`.  
  
 `riid`  
 \[in\] 인터페이스 식별자는 개체와 통신 하는 데 사용 합니다.  
  
 `ppvObject`  
 \[out\] `riid`에서 요청한 인터페이스 포인터를 받는 포인터 변수의 주소입니다.  반환이 성공적 이면, 시 \*`ppvObject` 요청 된 인터페이스 포인터를 포함 합니다.  실패, \*`ppvObject` 포함 `NULL`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 이렇게 위임 `CoCreateInstance`.  
  
## 참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)