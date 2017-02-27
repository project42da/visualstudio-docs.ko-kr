---
title: "IDebugPortSupplier3::CanPersistPorts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier3::CanPersistPorts"
helpviewer_keywords: 
  - "IDebugPortSupplier3::CanPersistPorts"
ms.assetid: 4127760c-e602-4e86-9232-457e382a52c7
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugPortSupplier3::CanPersistPorts
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 포트 공급자 포트 \(해당 디스크에 기록 하 여\) 디버거가 호출 사이 지속 될 수 있는지 확인 합니다.  
  
## 구문  
  
```cpp  
HRESULT CanPersistPorts();  
```  
  
```c#  
int CanPersistPorts();  
```  
  
#### 매개 변수  
 없음  
  
## 반환 값  
 `S_OK`포트 유지 될 수 있는 경우 또는 `S_FALSE` 포트를 유지할 수 없습니다 나타낼 수 있습니다.  
  
## 설명  
 포트 포트 공급자에 저장 하는 경우 소멸 될 때 작업을 수행 하 고 다시 인스턴스화될 때이 다시 로드 해야 합니다.  
  
## 참고 항목  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)