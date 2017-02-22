---
title: "IDebugProcess2::Detach | Microsoft Docs"
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
  - "IDebugProcess2::Detach"
helpviewer_keywords: 
  - "IDebugProcess2::Detach"
ms.assetid: ee2b9084-2db1-4e49-a1d9-387284b7c3f8
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProcess2::Detach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

모든 프로그램의 프로세스에서 분리 하 여이 프로세스에서 디버거를 분리 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Detach(   
   void   
);  
```  
  
```c#  
int Detach();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 모든 프로그램 및 프로세스 계속 실행 되지만 더 이상 디버그 세션의 일부가 아닙니다.  분리 작업에는 완벽 하 고 더 이상 디버그 이벤트에 대해이 프로세스 \(프로그램\)를 보낸 후.  
  
## 참고 항목  
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)