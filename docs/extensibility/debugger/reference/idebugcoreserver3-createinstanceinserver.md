---
title: "IDebugCoreServer3::CreateInstanceInServer | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugCoreServer3::CreateInstanceInServer"
helpviewer_keywords: 
  - "IDebugCoreServer3::CreateInstanceInServer"
ms.assetid: 76f36bae-f6ab-413c-a8a9-8808bfeba05b
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugCoreServer3::CreateInstanceInServer
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진의 인스턴스를 서버에 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT CreateInstanceInServer(  
   LPCWSTR  szDll,  
   WORD     wLangId,  
   REFCLSID clsidObject,  
   REFIID   riid,  
   void**   ppvObject  
);  
```  
  
```c#  
int CreateInstanceInServer(  
   string     szDll,   
   ushort     wLangID,   
   ref Guid   clsidObject,   
   ref Guid   riid,   
   out IntPtr ppvObject  
);  
```  
  
#### 매개 변수  
 `szDll`  
 \[in\] 지정 된 CLSID를 구현 하는 dll의 경로 `clsidObject` 매개 변수.  이 경우 `NULL`, 다음 COM의 `CoCreateInstance` 함수를 호출 합니다.  
  
 `wLangId`  
 \[in\] 디버그 엔진의 로캘입니다.  경우는 0입니다 있는 [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md) 메서드를 호출 하면 안 됩니다.  
  
 `clsidObject`  
 \[in\] 디버그 엔진의 CLSID에 만들 수 있습니다.  
  
 `riid`  
 \[in\] 클래스에서 개체를 검색 하려면 인터페이스의 인터페이스 ID는 특정.  
  
 `ppvObject`  
 \[out\] `IUnknown` 인터페이스에서 인스턴스화된 개체입니다.  캐스팅 또는이 개체를 사용 하 여 원하는 인터페이스를 마샬링해야 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugCoreServer3](../../../extensibility/debugger/reference/idebugcoreserver3.md)   
 [SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)