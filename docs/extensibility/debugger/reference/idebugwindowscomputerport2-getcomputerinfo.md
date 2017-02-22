---
title: "IDebugWindowsComputerPort2::GetComputerInfo | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "GetComputerInfo"
  - "IDebugWindowsComputerPort2::GetComputerInfo"
ms.assetid: 654910b2-c239-44c8-92fc-317680a5672f
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugWindowsComputerPort2::GetComputerInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

컴퓨터에 대 한 정보를 검색 합니다. 디버거를 실행 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetComputerInfo(  
   COMPUTER_INFO * pInfo  
);  
```  
  
```c#  
public int GetComputerInfo(  
   out COMPUTER_INFO[] pInfo  
);  
```  
  
#### 매개 변수  
 `pInfo`  
 \[out\] 컴퓨터 정보를 포함 하는 구조체에 대 한 참조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugWindowsComputerPort2](../../../extensibility/debugger/reference/idebugwindowscomputerport2.md)   
 [COMPUTER\_INFO](../../../extensibility/debugger/reference/computer-info.md)