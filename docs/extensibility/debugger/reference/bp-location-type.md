---
title: "BP_LOCATION_TYPE | Microsoft Docs"
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
  - "BP_LOCATION_TYPE"
helpviewer_keywords: 
  - "BP_LOCATION_TYPE 구조"
ms.assetid: 0248430a-3b61-4809-87a9-e9b6bb7d1130
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# BP_LOCATION_TYPE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

중단점 중단점 요청에 대 한 위치 형식을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
typedef DWORD BP_LOCATION_TYPE;  
```  
  
```c#  
public enum enum_BP_LOCATION_TYPE {   
   BPLT_NONE               = 0x00000000,  
   BPLT_FILE_LINE          = 0x00010000,  
   BPLT_FUNC_OFFSET        = 0x00020000,  
   BPLT_CONTEXT            = 0x00030000,  
   BPLT_STRING             = 0x00040000,  
   BPLT_ADDRESS            = 0x00050000,  
   BPLT_RESOLUTION         = 0x00060000,  
   BPLT_CODE_FILE_LINE     = BPT_CODE | BPLT_FILE_LINE,  
   BPLT_CODE_FUNC_OFFSET   = BPT_CODE | BPLT_FUNC_OFFSET,  
   BPLT_CODE_CONTEXT       = BPT_CODE | BPLT_CONTEXT,  
   BPLT_CODE_STRING        = BPT_CODE | BPLT_STRING,  
   BPLT_CODE_ADDRESS       = BPT_CODE | BPLT_ADDRESS ,  
   BPLT_DATA_STRING        = BPT_DATA | BPLT_STRING,  
   BPLT_TYPE_MASK          = 0x0000FFFF,  
   BPLT_LOCATION_TYPE_MASK = 0xFFFF0000  
};  
```  
  
## Members  
 BPLT\_NONE  
 없음 중단점 위치를 지정합니다.  
  
 BPLT\_FILE\_LINE  
 중단점 위치에 파일 줄으로 지정합니다.  
  
 BPLT\_FUNC\_OFFSET  
 중단점 위치 함수 오프셋으로 지정합니다.  
  
 BPLT\_CONTEXT  
 중단점의 위치를 컨텍스트로 지정합니다.  
  
 BPLT\_STRING  
 중단점 위치 형식 문자열을 지정합니다.  
  
 BPLT\_ADDRESS  
 중단점 위치 형식으로 주소를 지정합니다.  
  
 BPLT\_RESOLUTION  
 중단점 위치 형식으로 해상도 지정합니다.  
  
 BPLT\_CODE\_FILE\_LINE  
 중단점의 위치는 소스 코드 줄으로 지정합니다.  
  
 BPLT\_CODE\_FUNC\_OFFSET  
 중단점의 위치 하는 코드 함수가 오프셋으로 지정합니다.  
  
 BPLT\_CODE\_CONTEXT  
 중단점의 위치와 코드 컨텍스트에 지정합니다.  
  
 BPLT\_CODE\_STRING  
 중단점 위치 형식 코드 문자열을 지정합니다.  
  
 BPLT\_CODE\_ADDRESS  
 중단점의 위치를 코드 주소로 지정합니다.  
  
 BPLT\_DATA\_STRING  
 중단점 위치 형식 데이터 문자열을 지정합니다.  
  
 BPLT\_TYPE\_MASK  
 중단점 형식의 값을 추출할 수 있도록 하는 비트 마스크를 지정 합니다.  
  
 BPLT\_LOCATION\_TYPE\_MASK  
 중단점 위치 형식 값을 추출할 수 있도록 하는 비트 마스크를 지정 합니다.  
  
## 설명  
 매개 변수로 전달 되는 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md) 메서드.  
  
 중단점 위치 형식 중단점 형식 위치 형식으로 이루어집니다.  따라서 중단점 위치 형식에는 중단점 형식입니다 \(예를 들어, `BPT_CODE`\) 또는 위치 유형 \(예를 들어, `BPLT_FILE_LINE`\).  현재 지원 되는 모든 중단점 위치 형식에 대해 미리 정의 된 상수는이 열거형에 포함 됩니다 \(`BPLT_CODE_FILE_LINE` \- `BPLT_DATA_STRING`\).  
  
 `BPT_CODE` 및 `BPT_DATA`는 [BP\_TYPE](../../../extensibility/debugger/reference/bp-type.md) 열거형의 멤버입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetLocationType](../../../extensibility/debugger/reference/idebugbreakpointrequest2-getlocationtype.md)   
 [BP\_TYPE](../../../extensibility/debugger/reference/bp-type.md)