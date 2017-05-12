---
title: "IActiveScriptSiteDebug::GetApplication | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSiteDebug.GetApplication
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSiteDebug::GetApplication"
ms.assetid: 4400f1b1-3108-4a71-b1f1-43586fe1227c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSiteDebug::GetApplication
이 스크립트 사이트와 연관 된 디버그 응용 프로그램 개체를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetApplication(  
   IDebugApplication**  ppda  
);  
```  
  
#### 매개 변수  
 `ppda`  
 \[out\] 스크립트 사이트와 연관 된 디버그 응용 프로그램 개체에 대 한 포인터입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|디버깅 호스트 직접 지원 하지 않습니다.|  
  
## 설명  
 `GetApplication` 메서드는 각 스크립트에 속한 응용 프로그램 개체를 정의 하는 스마트 호스트를 제공 합니다.  포함 된 응용 프로그램을 사용 하는이 메서드를 호출 하는 스크립트 엔진 좋으며 `IProcessDebugManager::GetDefaultApplication` 이 실패 한 경우.  
  
## 참고 항목  
 [IActiveScriptSiteDebug 인터페이스](../../winscript/reference/iactivescriptsitedebug-interface.md)   
 [IProcessDebugManager::GetDefaultApplication](../../winscript/reference/iprocessdebugmanager-getdefaultapplication.md)