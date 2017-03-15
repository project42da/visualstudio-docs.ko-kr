---
title: "PROCESS_INFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROCESS_INFO"
helpviewer_keywords: 
  - "PROCESS_INFO 구조"
ms.assetid: 260c33cc-a05e-4645-84b6-536d0b3b0537
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# PROCESS_INFO
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스에 대 한 정보가 포함 되어 있습니다.  
  
## 구문  
  
```cpp#  
typedef struct tagPROCESS_INFO {   
   PROCESS_INFO_FIELDS Fields;  
   BSTR                bstrFileName;  
   BSTR                bstrBaseName;  
   BSTR                bstrTitle;  
   AD_PROCESS_ID       ProcessId;  
   DWORD               dwSessionId;  
   BSTR                bstrAttachedSessionName;  
   FILETIME            CreationTime;  
   PROCESS_INFO_FLAGS  Flags;  
} PROCESS_INFO;  
```  
  
```c#  
public struct PROCESS_INFO {   
   public uint          Fields;  
   public string        bstrFileName;  
   public string        bstrBaseName;  
   public string        bstrTitle;  
   public AD_PROCESS_ID ProcessId;  
   public uint          dwSessionId;  
   public string        bstrAttachedSessionName;  
   public FILETIME      CreationTime;  
   public uint          Flags;  
};  
```  
  
## Members  
 필드  
 플래그의 조합에서 [PROCESS\_INFO\_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md) 채워진 필드를 지정 하는 열거형입니다.  
  
 bstrFileName  
 과정의 전체 경로 이름입니다.  전화에 해당 하는 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) 메서드 매개 변수로 `GN_FILENAME`.  
  
 bstrBaseName  
 파일 이름 및 확장명 프로세스입니다.  전화에 해당 하는 `IDebugProcess2::Getname` 메서드 매개 변수로 `GN_BASENAME`.  
  
 bstrTitle  
 있는 경우 프로세스의 제목입니다.  전화에 해당 하는 `IDebugProcess2::Getname` 메서드 매개 변수로 `GN_TITLE`.  
  
 ProcessId  
 [AD\_PROCESS\_ID](../../../extensibility/debugger/reference/ad-process-id.md) 프로세스를 식별 하는 구조입니다.  전화에 해당 하는 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md) 메서드.  
  
 dwSessionId  
 이 프로세스를 실행 하면 디버그 세션의 식별자입니다.  
  
 bstrAttachedSessionName  
 연결 된 세션 이름입니다.  전화에 해당 하는 [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md) 메서드.  
  
 CreationTime  
 프로세스가 생성 된 시간입니다.  
  
 Flags  
 플래그의 조합에서 [PROCESS\_INFO\_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md) 프로세스의 속성을 지정 하는 열거형입니다.  
  
## 설명  
 이 구조체에 전달 되는 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md) 메서드는 입력 위치에 있습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [PROCESS\_INFO\_FIELDS](../../../extensibility/debugger/reference/process-info-fields.md)   
 [PROCESS\_INFO\_FLAGS](../../../extensibility/debugger/reference/process-info-flags.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugprocess2-getinfo.md)   
 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)   
 [GetPhysicalProcessId](../../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)   
 [GetAttachedSessionName](../../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)