---
title: "IDiaLoadCallback::NotifyOpenDBG | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaLoadCallback::NotifyOpenDBG 메서드"
ms.assetid: dbc4dcf0-4ace-4dce-9790-0fdaf3a23d3b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaLoadCallback::NotifyOpenDBG
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

후보.dbg 파일을 열 때 호출 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT NotifyOpenDBG (   
   LPCOLESTR dbgPath,  
   HRESULT   resultCode  
);  
```  
  
#### 매개 변수  
 `dbgPath`  
 \[in\] .Dbg 파일의 전체 경로입니다.  
  
 `resultCode`  
 \[in\] 성공 여부를 나타내는 코드 \(`S_OK`\) 또는이 파일에 적용 되는 로드에 실패 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 코드는 일반적으로 무시 됩니다.  
  
## 참고 항목  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)