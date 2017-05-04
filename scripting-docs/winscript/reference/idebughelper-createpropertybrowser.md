---
title: "IDebugHelper::CreatePropertyBrowser | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugHelper.CreatePropertyBrowser
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugHelper::CreatePropertyBrowser"
ms.assetid: 2fa819cf-c7f7-4bd7-b018-ea33b804ba8f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugHelper::CreatePropertyBrowser
VARIANT를 래핑하는 속성 브라우저에 반환 합니다.  
  
## 구문  
  
```  
HRESULT CreatePropertyBrowser(  
   VARIANT*                  pvar,  
   LPCOLESTR                 bstrName,  
   IDebugApplicationThread*  pdat,  
   IDebugProperty**          ppdob  
);  
```  
  
#### 매개 변수  
 `pvar`  
 \[in\] 루트 variant를 찾아볼 수 있습니다.  
  
 `bstrName`  
 \[in\] 루트를 제공 하는 이름입니다.  
  
 `pdat`  
 \[in\] 스레드는 속성을 요청할 수 있습니다.  이 매개 변수는 NULL 이면 없음 마샬링 수행 됩니다.  
  
 `ppdob`  
 \[out\] 속성 브라우저입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 VARIANT를 래핑하는 속성 브라우저에 대 한 반환 됩니다.  
  
## 참고 항목  
 [IDebugHelper::CreatePropertyBrowserEx](../../winscript/reference/idebughelper-createpropertybrowserex.md)   
 [IDebugHelper 인터페이스](../../winscript/reference/idebughelper-interface.md)   
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)