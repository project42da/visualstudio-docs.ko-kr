---
title: "EncUnavailableReason | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "EncUnavailableReason"
helpviewer_keywords: 
  - "EncUnavailableReason 열거형"
ms.assetid: c10aa4c0-d7e0-4de1-b8ff-7e050985eb12
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# EncUnavailableReason
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

`This is for internal use only!`나타내는 이유는  **편집 하며 계속 하기** 를 사용할 수 없습니다.  
  
## 구문  
  
```cpp#  
enum tagEncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
typedef enum tagEncUnavailableReason EncUnavailableReason;  
```  
  
```c#  
public enum EncUnavailableReason {  
   ENCUN_NONE,  
   ENCUN_INTEROP,  
   ENCUN_SQLCLR,  
   ENCUN_MINIDUMP,  
   ENCUN_EMBEDDED,  
   ENCUN_ATTACH,  
   ENCUN_WIN64  
};  
```  
  
#### 매개 변수  
 ENCUN\_NONE  
 편집 하며 계속 하기 없는 사용할 수 없는 특정 이유입니다.  
  
 ENCUN\_INTEROP  
 편집 하며 계속 하기 사용할 수 없습니다 동안 InterOp 호출이 있습니다.  
  
 ENCUN\_SQLCLR  
 편집 하며 계속 하기 수 없습니다 사용할 수 있는 공용 언어 런타임 \(CLR\)을 사용 하 여 SQL 프로시저 호출 동안.  
  
 ENCUN\_MINIDUMP  
 편집 하며 계속 하기 사용할 수 없습니다 미니 덤프를 생성을 처리 하는 동안.  
  
 ENCUN\_EMBEDDED  
 편집 하며 계속 하기 사용할 수 없습니다 포함 된 코드를 처리 하는 동안.  
  
 ENCUN\_ATTACH  
 편집 하며 계속 되어 사용할 수 없는 세션에 연결 되어 있기 때문에 시작 되지 않습니다 디버거에 의해.  
  
 ENCUN\_WIN64  
 편집 하며 계속 하기 사용할 수 없습니다 Windows 64 비트 코드를 처리 하는 동안.  
  
## 설명  
 이 열거형은 하입니다 [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)].  [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md) 및 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md) 사용자 지정 포트 공급자가 구현 된 메서드를 반환 합니다 항상 `E_NOTIMPL`.  
  
## 요구 사항  
 헤더: msdbg.idl  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [DisableENC](../../../extensibility/debugger/reference/idebugprocess3-disableenc.md)   
 [GetENCAvailableState](../../../extensibility/debugger/reference/idebugprocess3-getencavailablestate.md)