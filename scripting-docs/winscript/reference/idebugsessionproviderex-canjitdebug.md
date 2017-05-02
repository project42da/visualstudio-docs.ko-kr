---
title: "IDebugSessionProviderEx:CanJITDebug | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugSessionProviderEx:CanJITDebug
apilocation: scrobj.dll
ms.assetid: 68f91bed-ca69-46b5-b517-ca9ca80b8803
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDebugSessionProviderEx:CanJITDebug
지정 된 프로세스 디버깅 Just In Time 디버깅을 할 수 있는지 여부를 결정 합니다.  
  
## 구문  
  
```  
HRESULT CanJITDebug(  
   DWORD  pid  
);  
```  
  
#### 매개 변수  
 `pid`  
 \[in\] 디버깅할 프로세스의 프로세스 식별자입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
  
## 참고 항목  
 [IDebugSessionProviderEx 인터페이스](../../winscript/reference/idebugsessionproviderex-interface.md)