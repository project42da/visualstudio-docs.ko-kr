---
title: "IDebugProviderProgramNode2::UnmarshalDebuggeeInterface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProviderProgramNode2::UnmarshalDebuggeeInterface"
helpviewer_keywords: 
  - "IDebugProviderProgramNode2::UnmarshalDebuggeeInterface"
ms.assetid: 2e4653c5-10f1-493c-9973-f31d266c5d48
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProviderProgramNode2::UnmarshalDebuggeeInterface
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스 경계에 걸쳐 특정된 인터페이스를 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT UnmarshalDebuggeeInterface(  
   REFIID riid,  
   void** ppvObject  
);  
```  
  
```c#  
int UnmarshalDebuggeeInterface(  
   ref Guid   riid,  
   out IntPtr ppvObject  
);  
```  
  
#### 매개 변수  
 `riid`  
 \[in\] 가져올 인터페이스의 GUID입니다.  
  
 `ppvObject`  
 \[out\] 원하는 인터페이스를 구현 하는 개체를 반환 합니다.  \[C \+ \+\]이 직접 원하는 인터페이스 형식으로 캐스팅 될 수 있습니다.  \[C\#\] 사용의 <xref:System.Runtime.InteropServices.Marshal.GetObjectForIUnknown%2A> 메서드는 원하는 인터페이스를 가져올 수 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버그 엔진을 실행 하는 경우이 메서드는 사용 되는 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] 프로세스 공간 및 디버깅 중인 프로그램은 자체 프로세스 공간에서 실행 됩니다.  
  
## 참고 항목  
 [IDebugProviderProgramNode2](../../../extensibility/debugger/reference/idebugproviderprogramnode2.md)