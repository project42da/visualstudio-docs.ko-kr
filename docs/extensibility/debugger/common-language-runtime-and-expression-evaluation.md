---
title: "공용 언어 런타임 및 식 평가 | Microsoft Docs"
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
  - "식 평가 및 공용 언어 런타임"
ms.assetid: b36c1eb5-1aaf-48a6-b287-ee7a273d2b1c
caps.latest.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 15
---
# 공용 언어 런타임 및 식 평가
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

> [!IMPORTANT]
>  Visual Studio 2015의 식 계산기를 구현 합니다. 이러한 방식으로 사용 되지 않습니다. CLR 식 계산기를 구현 하는 방법에 대 한 정보를 참조 하십시오 [CLR 식 계산기](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) 및 [관리 되는 식 계산기 예제](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)합니다.  
  
 컴파일러, Visual Basic 및 C\# \(C 형 발음\), 공용 언어 런타임 \(CLR\)을 대상으로 하는 MSIL을 생성 Microsoft 중간 언어 \(\), 이후 인와 같은 네이티브 코드로 컴파일됩니다. CLR \(DE\) 결과 코드를 디버깅 하는 디버그 엔진을 제공 합니다. 독점 프로그래밍 언어를 Visual Studio IDE에 통합 하려는 경우에 MSIL로 컴파일하려면 선택할 수 있으며 없으므로 직접 DE를 작성 하. 그러나 프로그래밍 언어의 컨텍스트 내에서 식을 계산할 수 있는 식 계산기 \(EE\)을 작성 해야 합니다.  
  
## 토론  
 조작 하는데 사용 되는 연산자의 집합 및 데이터 개체의 집합을 생성 하는 컴퓨터 언어 식은 구문 분석 일반적으로 됩니다. 예를 들어 데이터에 더하기 연산자 \(\+\)를 적용 하려면 분석할 수 있습니다 "A \+ B" 식 "A"와 "B" 다른 데이터 개체에 발생할 수 있으므로 개체입니다. 데이터 개체, 연산자 및 해당 연결의 전체 집합 연산자에는 트리 노드 및 분기에 있는 데이터 개체 트리로 프로그램에서 가장 자주 표시 됩니다. 트리 형식으로 분류 되어 있는 식은 구문 분석 된 트리를 이라고 합니다.  
  
 식을 구문 분석 되 면 각 데이터 개체를 평가 하는 기호 공급자 \(SP\) 라고 합니다. 예를 들어, "A"는 둘 이상의 메서드를 다음 질문에 모두 정의 되어 있으면 "는 A?" A의 값을 조사할 수 있습니다 전에 응답 해야 합니다. SP에서 반환 된 응답은 "다섯 번째 스택 프레임에 세 번째 항목" 또는 "이 메서드에 정적 메모리의 시작 부분 외 50 바이트를 할당 된."  
  
 프로그램 자체에 대 한 MSIL을 생성, 외에도 CLR 컴파일러는 프로그램 데이터베이스 \(.pdb\) 파일에 작성 하는 매우 설명 디버깅 정보를 만들어 수도 있습니다. 소유 언어 컴파일러는 같은 형식으로 CLR 컴파일러에서 디버그 정보를 생성, CLR의 SP으로 언어의 명명 된 데이터 개체를 식별할 수 있습니다. 명명 된 데이터 개체를 식별 되 면 EE 바인더 개체를 해당 개체의 값을 보유 하는 메모리 영역에 데이터 개체를 연결 \(또는 바인딩\)를 사용 합니다. 다음은 DE 가져오거나 데이터 개체에 대 한 새 값을 설정할 수 있습니다.  
  
 전용 컴파일러를 호출 하 여 디버깅 정보는 CLR을 제공할 수는 `ISymbolWriter` 인터페이스 \(.NET Framework 네임 스페이스에서에 정의 된 `System.Diagnostics.SymbolStore`\). MSIL로 컴파일 하 고 이러한 인터페이스를 통해 디버그 정보를 작성, 전용 컴파일러 및 사용 하 여 CLR DE SP. 이 크게 Visual Studio IDE에는 자체 언어 통합 간소화 합니다.  
  
 CLR DE 식을 계산 하는 독점 EE를 호출할 때는 DE EE SP 및 바인더 개체에 대 한 인터페이스를 제공 합니다. 따라서 CLR 기반 디버그 엔진 의미를 쓰는 것이;에서 적절 한 식 계산기 인터페이스를 구현 하는 데에 필요 바인딩 및 사용자에 대 한 처리 기호 CLR을 처리 합니다.  
  
## 참고 항목  
 [CLR 식 계산기를 작성합니다.](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)