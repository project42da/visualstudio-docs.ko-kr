---
title: "로컬 값을 변경 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [디버깅 SDK], 식 계산"
  - "프로그래밍 방식으로 값을 변경 하는 식 계산"
ms.assetid: 8407d3df-d38a-4328-82d1-98084bef43ec
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 로컬 값을 변경
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 값 필드에 새 값을 입력 한 경우는 **지역** 창 디버그 패키지 전달에서 문자열을 식 계산기 \(EE\)을 입력 합니다. EE 간단한 값 또는 식을 포함할 수 있으며 연결 된 로컬의 결과 값을 저장 된이 문자열을 평가 합니다.  
  
 다음은 로컬 값을 변경 하는 프로세스의 개요입니다.  
  
1.  Visual Studio를 호출 하는 사용자가 새 값을 입력 한 후 [SetValueAsString](../../extensibility/debugger/reference/idebugproperty2-setvalueasstring.md) 에 [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md) 로컬 연관 된 개체입니다.  
  
2.  `IDebugProperty2::SetValueAsString` 다음 작업을 수행합니다.  
  
    1.  값을 생성 하는 문자열을 평가 합니다.  
  
    2.  연결 된 바인딩합니다 [IDebugField](../../extensibility/debugger/reference/idebugfield.md) 가져올 개체는 [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) 개체입니다.  
  
    3.  일련의 바이트를 변환합니다.  
  
    4.  호출 [SetValue](../../extensibility/debugger/reference/idebugobject-setvalue.md) 디버깅 중인 프로그램에 액세스할 수 있도록 메모리를 값의 바이트를 설정 합니다.  
  
3.  Visual Studio을 새로 고치는 **지역** 표시 \(참조 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md) 대 한 자세한 내용은\).  
  
 변수 값을 변경 하려면이 절차는 또한는 **조사식** 창을 제외 하 고는 `IDebugProperty2` 대신 사용 되는 지역 변수의 값과 관련 된 개체는 `IDebugProperty2` 로컬 자체와 연결 된 개체입니다.  
  
## 단원 내용  
 [변경 된 값의 샘플 구현](../../extensibility/debugger/sample-implementation-of-changing-values.md)  
 MyCEE 샘플을 사용 하 여 값을 변경 하는 과정을 단계별로 실행 되도록 합니다.  
  
## 참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)   
 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)