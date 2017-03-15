---
title: "IDebugFunctionObject2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugFunctionObject2 인터페이스"
ms.assetid: 56b2fdff-146d-4138-a34c-59a9c65a3ddd
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugFunctionObject2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 함수를 나타내는 및 성능 향상은 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
## 구문  
  
```  
IDebugFunctionObject2 : IUnknown  
```  
  
## 구현자를 위한 정보  
 식 계산기 \(EE\) 함수를 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스의 메서드를 지연의 **IDebugFunctionObject** 다음과 같은 방법으로:  
  
-   **IDebugEvaluate** 메서드는 플래그를 사용 합니다.  
  
-   **CreateObject** 플래그 및 제한 메서드를 사용 합니다.  
  
-   **CreateStringObjectWithLength** 메서드 길이 사용 합니다.  
  
## 메서드  
 이 인터페이스는 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject2-createobject.md)|플래그 설정을 평가 하 고 시간 제한 값을 지정 하는 생성자를 사용 하는 개체를 만듭니다.|  
|[CreateStringObjectWithLength](../../../extensibility/debugger/reference/idebugfunctionobject2-createstringobjectwithlength.md)|지정된 된 길이가 있는 문자열 개체를 만듭니다.|  
|[평가](../../../extensibility/debugger/reference/idebugfunctionobject2-evaluate.md)|함수를 호출 하 고 결과 값으로 개체를 반환 합니다.|  
  
## 요구 사항  
 헤더: Ee.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll