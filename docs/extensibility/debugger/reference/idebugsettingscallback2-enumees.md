---
title: "IDebugSettingsCallback2::EnumEEs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugSettingsCallback2::EnumEEs"
ms.assetid: 9f884c49-426f-461b-b547-9d909486e73f
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugSettingsCallback2::EnumEEs
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

공급 업체 및 언어 식별자를 지정 합니다. 사용할 수 있는 식 계산기를 열거 합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumEEs(  
   DWORD  celtBuffer,  
   GUID*  rgguidLang,  
   GUID*  rgguidVendor,  
   DWORD* pceltEEs  
);  
```  
  
```c#  
public int EnumEEs(  
   uint       celtBuffer,  
   ref Guid   rgguidLang,  
   ref Guid   rgguidVendor,  
   ref uint[] pceltEEs  
);  
```  
  
#### 매개 변수  
 `celtBuffer`  
 \[in\] 요소의 수는 `pceltEEs` 버퍼입니다.  
  
 `rgguidLang`  
 \[in, out\] 프로그래밍 언어에 대 한 고유 식별자입니다.  
  
 `rgguidVendor`  
 \[in, out\] 공급 업체에 대 한 고유 식별자입니다.  
  
 `pceltEEs`  
 \[in, out\] 식 계산기의 배열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugSettingsCallback2](../../../extensibility/debugger/reference/idebugsettingscallback2.md)