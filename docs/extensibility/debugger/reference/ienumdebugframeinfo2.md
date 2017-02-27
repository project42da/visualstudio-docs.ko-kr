---
title: "IEnumDebugFrameInfo2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugFrameInfo2"
helpviewer_keywords: 
  - "IEnumDebugFrameInfo2"
ms.assetid: 994e30ad-435a-4f9e-9272-d96d9e01099c
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IEnumDebugFrameInfo2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 열거 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조체입니다.  
  
## 구문  
  
```  
IEnumDebugFrameInfo2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 현재 호출 스택을 구조 목록을 제공 하기 위해이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 Visual Studio [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) 중단점 때마다이 인터페이스를 취득 하려면 예외 또는 중단 디버깅 중인 프로그램에서 발생 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugFrameInfo2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugframeinfo2-next.md)|지정 된 수의 검색 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 에서 열거 시퀀스 구조입니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugframeinfo2-skip.md)|지정 된 개수의 생략 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 에서 열거 시퀀스 구조입니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugframeinfo2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugframeinfo2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugframeinfo2-getcount.md)|매핑되는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 열거자에서 구조.|  
  
## 설명  
 Visual Studio 디버깅 중인 프로그램의 일시 중지 사용자 생성, 중단점 또는 예외를 처리 하는 첫 단계는이 인터페이스를 가져옵니다.  목록에 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조는 현재 호출 스택에, 목록의 끝에 목록 및 가장 오래 된 함수의 시작 부분에 현재 함수 호출을 호출 합니다.  각 `FRAMEINFO` 식이 계산 될 수 있는 한 지역 변수 검색에서 컨텍스트 스택 프레임을 나타냅니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)