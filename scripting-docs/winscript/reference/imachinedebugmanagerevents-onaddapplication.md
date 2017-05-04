---
title: "IMachineDebugManagerEvents::onAddApplication | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IMachineDebugManagerEvents.onAddApplication
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IMachineDebugManagerEvents::onAddApplication"
ms.assetid: 00a54b91-36d5-430d-b654-5e2abe5300cd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IMachineDebugManagerEvents::onAddApplication
응용 프로그램 실행에 추가 될 때 이벤트를 처리 합니다. 응용 프로그램 목록입니다.  
  
## 구문  
  
```  
HRESULT onAddApplication(  
   IRemoteDebugApplication*  pda,  
   DWORD                     dwAppCookie  
);  
```  
  
#### 매개 변수  
 `pda`  
 \[in\] 응용 프로그램 실행에 추가 된 응용 프로그램 목록입니다.  
  
 `dwAppCookie`  
 \[in\] 응용 프로그램의 응용 프로그램 목록에 추가할 때 제공 되는 쿠키입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 메서드는 응용 프로그램 실행에 추가 했음을 나타냅니다 응용 프로그램 목록입니다.  
  
## 참고 항목  
 [IMachineDebugManagerEvents 인터페이스](../../winscript/reference/imachinedebugmanagerevents-interface.md)   
 [IMachineDebugManagerEvents::onRemoveApplication](../../winscript/reference/imachinedebugmanagerevents-onremoveapplication.md)