---
title: "공용 언어 런타임 식 계산기를 작성합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "식 계산기, 자습서"
  - "식 계산, 샘플"
  - "디버깅 [디버깅 SDK], 식 계산기 자습서"
ms.assetid: bd79d57f-8e0a-4e14-a417-0b1de28fa1b2
caps.latest.revision: 23
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 23
---
# 공용 언어 런타임 식 계산기를 작성합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 식 계산기 \(EE\) 구문을 처리 하는 디버그 엔진 \(DE\)의 일부 이며 디버깅 중인 코드를 생성 하는 프로그래밍 언어의 의미 체계입니다. 식 프로그래밍 언어의 컨텍스트 내에서 평가 되어야 합니다. 예를 들어 일부 언어에서 식 "A \+ B"은 "A의 합계와 B" 다른 언어에서는 같은 식 "A 또는 B."를 의미할 수도 있습니다. 따라서 별도 EE 작성 해야 Visual Studio IDE에서 코드를 디버깅할 개체를 생성 하는 각 프로그래밍 언어입니다.  
  
 Visual Studio 디버그 패키지의 일부 측면 프로그래밍 언어의 컨텍스트에서 코드를 해석 해야 합니다. 예를 들어 때 실행에서 중단에 사용자가 입력 한 모든 식이 중단점을 한 **조사식** 창을 평가 하 고 표시 해야 합니다. 사용자가에 식을 입력 하 여 지역 변수 값을 변경할 수는 또한는 **조사식** 창에는 **Immediate** 창.  
  
## 단원 내용  
 [공용 언어 런타임 및 식 평가](../../extensibility/debugger/common-language-runtime-and-expression-evaluation.md)  
 Visual Studio IDE에 자체 프로그래밍 언어를 통합 하는 경우는 EE 작성 독점 언어의 컨텍스트 내에서 식을 계산할 수 있는 컴파일할 수 있도록 Microsoft intermediate language \(MSIL\)로 디버그 엔진을 작성 하지 않고도 설명 합니다.  
  
 [식 계산기 아키텍처](../../extensibility/debugger/expression-evaluator-architecture.md)  
 필요한 EE 인터페이스를 구현 하 고 공용 언어 런타임 기호 공급자 \(SP\) 및 바인더 인터페이스를 호출 하는 방법에 설명 합니다.  
  
 [식 계산기를 등록 하는 중](../../extensibility/debugger/registering-an-expression-evaluator.md)  
 EE 등록 해야 자체 공용 언어 런타임 및 Visual Studio 런타임 환경 모두 클래스 팩터리로 인식 합니다.  
  
 [식 계산기를 구현합니다.](../../extensibility/debugger/implementing-an-expression-evaluator.md)  
 식의 계산 프로세스는 디버그 엔진 \(DE\), 기호 공급자 \(SP\), 바인더 개체 및 식 계산기 \(EE\)를 포함 하는 방법을 설명 합니다.  
  
 [지역 변수를 표시합니다.](../../extensibility/debugger/displaying-locals.md)  
 방법, 실행이 일시 중지, 디버그 패키지가 로컬 변수 및 인수 목록을 얻으려면 DE 호출에 대해 설명 합니다.  
  
 [조사식 창 식 평가](../../extensibility/debugger/evaluating-a-watch-window-expression.md)  
 Visual Studio 디버그 패키지는 조사 목록에 각 식의 현재 값을 확인 하는 DE를 호출 하는 방법에 대해 설명 합니다.  
  
 [로컬 값을 변경](../../extensibility/debugger/changing-the-value-of-a-local.md)  
 로컬 값을 변경에서 지역 창의 각 줄에 이름, 형식 및 지역 변수의 현재 값을 제공 하는 관련된 개체에 설명 합니다.  
  
 [시각화 도우미 형식 및 사용자 지정 뷰어를 구현합니다.](../../extensibility/debugger/implementing-type-visualizers-and-custom-viewers.md)  
 시각화 도우미 형식 및 사용자 지정 뷰어를 지원 하도록 구성 요소에 의해 구현 되어야 하는 데 필요한 인터페이스에 설명 합니다.  
  
## 참고 항목  
 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)