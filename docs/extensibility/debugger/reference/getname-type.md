---
title: "GETNAME_TYPE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GETNAME_TYPE"
helpviewer_keywords: 
  - "GETNAME_TYPE 열거형"
ms.assetid: 2f9f1679-e9e8-4c9c-ac90-aa07bfe69914
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# GETNAME_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

검색할 파일 이름 형식을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
typedef DWORD GETNAME_TYPE;  
```  
  
```c#  
public enum enum_GETNAME_TYPE {   
   GN_NAME         = 0,  
   GN_FILENAME     = 1,  
   GN_BASENAME     = 2,  
   GN_MONIKERNAME  = 3,  
   GN_URL          = 4,  
   GN_TITLE        = 5,  
   GN_STARTPAGEURL = 6  
};  
```  
  
## Members  
 GN\_NAME  
 문서 또는 상황에 맞는 이름을 지정합니다.  
  
 GN\_FILENAME  
 문서 또는 컨텍스트에서의 전체 경로 지정합니다.  
  
 GN\_BASENAME  
 문서 또는 컨텍스트의 전체 경로 대신 기본 파일 이름을 지정합니다.  
  
 GN\_MONIKERNAME  
 문서 또는 상황에 맞는 고유한 이름을 모니커 형식으로 지정합니다.  
  
 GN\_URL  
 문서 또는 컨텍스트는 URL 이름을 지정합니다.  
  
 GN\_TITLE  
 있는 경우 문서의 제목을 지정 합니다.  
  
 GN\_STARTPAGEURL  
 프로세스에 대 한 시작 페이지 URL을 가져옵니다.  
  
## 설명  
 이러한 값을 매개 변수로 전달 되는 [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md), [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md), 및 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md) 종류를 반환 하려면 name 속성을 지정 하는 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetName](../../../extensibility/debugger/reference/idebugdocument2-getname.md)   
 [GetName](../../../extensibility/debugger/reference/idebugdocumentcontext2-getname.md)   
 [GetName](../../../extensibility/debugger/reference/idebugprocess2-getname.md)