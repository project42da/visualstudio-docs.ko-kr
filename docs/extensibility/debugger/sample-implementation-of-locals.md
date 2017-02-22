---
title: "지역 변수의 샘플 구현 | Microsoft Docs"
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
  - "디버깅 [디버깅 SDK], 지역 변수"
  - "식 계산, 지역 변수"
ms.assetid: 66a2e00a-f558-4e87-96b8-5ecf5509e04c
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 지역 변수의 샘플 구현
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 Visual Studio에서 식 계산기 \(EE\)에서 메서드에 대 한 지역 변수를 얻는 방법의 개요는 다음과 같습니다.  
  
1.  Visual Studio에서 디버그 엔진 \(DE\) 호출 [GetDebugProperty](../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) 가져오려는 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 지역 변수를 포함 하는 스택 프레임의 모든 속성을 나타내는 개체입니다.  
  
2.  `IDebugStackFrame2::GetDebugProperty` 호출 [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md) 중단점이 발생 하는 메서드를 설명 하는 개체를 얻을 수 있습니다. 기호 공급자를 제공 하는 DE \([IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)\), 주소 \([IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)\), 및는 바인더 \([IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)\).  
  
3.  `IDebugExpressionEvaluator::GetMethodProperty` 호출 [GetContainerField](../../extensibility/debugger/reference/idebugsymbolprovider-getcontainerfield.md) 제공 된 `IDebugAddress` 가져올 개체는 [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) 지정된 된 주소를 포함 하는 메서드를 나타내는 합니다.  
  
4.  `IDebugContainerField` 인터페이스에 대 한 쿼리는 [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) 인터페이스입니다. 메서드의 지역에 대 한 액세스를 제공 하는이 인터페이스입니다.  
  
5.  `IDebugExpressionEvaluator::GetMethodProperty` 클래스를 인스턴스화합니다 \(라는 `CFieldProperty` 샘플에서\)를 구현 하는 `IDebugProperty2` 메서드의 지역 변수를 나타내는 인터페이스입니다.`IDebugMethodField` 개체는이 배치 됩니다 `CFieldProperty` 와 함께 개체는 `IDebugSymbolProvider`, `IDebugAddress` 및 `IDebugBinder` 개체입니다.  
  
6.  때는 `CFieldProperty` 개체를 초기화할 [GetInfo](../../extensibility/debugger/reference/idebugfield-getinfo.md) 라고 하는 `IDebugMethodField` 가져올 개체는 [FIELD\_INFO](../../extensibility/debugger/reference/field-info.md) 메서드 자체에 대 한 모든 표시할 수 있는 정보가 포함 된 구조체입니다.  
  
7.  `IDebugExpressionEvaluator::GetMethodProperty` 반환 된 `CFieldProperty` 개체는 `IDebugProperty2` 개체입니다.  
  
8.  Visual Studio 호출 [EnumChildren](../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) 반환 된 `IDebugProperty2` 필터와 개체 `guidFilterLocalsPlusArgs`합니다. 반환 합니다.는 [IEnumDebugPropertyInfo2](../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) 메서드의 지역 변수를 포함 하는 개체입니다. 이 열거형에 대 한 호출에 의해 채워진 [EnumLocals](../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) 및 [EnumArguments](../../extensibility/debugger/reference/idebugmethodfield-enumarguments.md)합니다.  
  
9. Visual Studio 호출 [다음](../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md) 얻으려고는 [DEBUG\_PROPERTY\_INFO](../../extensibility/debugger/reference/debug-property-info.md) 각 로컬에 대 한 구조입니다. 이 구조에 대 한 포인터를 포함 한 `IDebugProperty2` 로컬에 대 한 인터페이스입니다.  
  
10. Visual Studio 호출 [GetPropertyInfo](../../extensibility/debugger/reference/idebugproperty2-getpropertyinfo.md) 각 로컬 지역 변수의 이름, 값 및 형식을 얻으려고 합니다. 이에 표시 되는 정보는 **지역** 창입니다.  
  
## 단원 내용  
 [GetMethodProperty 구현](../../extensibility/debugger/implementing-getmethodproperty.md)  
 구현에 설명 [GetMethodProperty](../../extensibility/debugger/reference/idebugexpressionevaluator-getmethodproperty.md)합니다.  
  
 [지역 변수를 열거합니다.](../../extensibility/debugger/enumerating-locals.md)  
 디버그 엔진 \(DE\) 열거 지역 변수 또는 인수에 대 한 호출을 사용 하는 방법을 설명 합니다.  
  
 [로컬 속성 가져오기](../../extensibility/debugger/getting-local-properties.md)  
 DE 이름, 형식 및 하나 이상의 지역 변수의 값 가져오기에 대 한 호출을 사용 하는 방법에 대해 설명 합니다.  
  
 [로컬 값 가져오기](../../extensibility/debugger/getting-local-values.md)  
 평가 컨텍스트에 제공한 바인더 개체의 서비스를 필요로 하는 지역 변수의 값을 가져오는 방법을 설명 합니다.  
  
 [지역 변수를 평가합니다.](../../extensibility/debugger/evaluating-locals.md)  
 지역 변수를 평가 하는 방법에 대해 설명 합니다.  
  
## 관련 단원  
 [평가 컨텍스트](../../extensibility/debugger/evaluation-context.md)  
 식 계산기 \(EE\)을 호출 하는 DE 때 전달 되는 인수를 제공 합니다.  
  
 [MyCEE Sample](http://msdn.microsoft.com/ko-kr/624a018b-9179-402f-9d48-3aec87b48f4f)  
 구현 하는 접근 방식을 MyC 언어에 대 한 식 계산기를 만드는 방법을 보여 줍니다.  
  
## 참고 항목  
 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)