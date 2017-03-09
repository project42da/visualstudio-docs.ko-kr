---
title: "FxCopCmd 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "FxCopCmd 오류"
ms.assetid: bb614ed0-1b7c-4b56-99ae-da50ef6cfef9
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "susanno"
manager: "douge"
---
# FxCopCmd 오류
FxCopCmd는 모든 오류가 치명적이라고 인식하지는 않습니다.  FxCopCmd에 부분 분석을 수행하기에 충분한 정보가 있는 경우에는 분석을 수행하고 발생한 오류를 보고합니다.  32비트 정수인 오류 코드에는 오류에 해당하는 숫자 값의 비트 조합이 있습니다.  
  
 다음 표에서는 FxCopCmd가 반환하는 오류 코드에 대해 설명합니다.  
  
|오류|숫자 값|  
|--------|----------|  
|오류 없음|0x0|  
|분석 오류|0x1|  
|규칙 예외|0x2|  
|프로젝트 로드 오류|0x4|  
|어셈블리 로드 오류|0x8|  
|규칙 라이브러리 로드 오류|0x10|  
|보고서 가져오기 로드 오류|0x20|  
|출력 오류|0x40|  
|명령줄 스위치 오류|0x80|  
|초기화 오류입니다.|0x100|  
|어셈블리 참조 오류|0x200|  
|BuildBreakingMessage|0x400|  
|알 수 없는 오류|0x1000000|  
  
 심각한 오류에 대해 분석 오류가 반환됩니다.  이는 분석을 완료할 수 없음을 나타냅니다.  해당하는 경우에는 오류 코드에 심각한 오류의 기본 원인도 포함되어 있습니다.  심각한 오류의 발생 원인으로는 다음과 같은 것이 있습니다.  
  
-   입력 내용이 충분하지 않아 분석을 수행할 수 없습니다.  
  
-   분석에서 FxCopCmd가 처리하지 않는 예외를 throw합니다.  
  
-   지정한 프로젝트 파일이 없거나 손상되었습니다.  
  
-   출력 옵션이 지정되지 않았거나 파일을 쓸 수 없습니다.  
  
    > [!NOTE]
    >  FxCopCmd 반환 코드인 "어셈블리 참조 오류" 0x200 자체는 오류가 아닌 경고입니다.  이 반환 코드는 누락된 간접 참조가 발견되었지만 FxCopCmd에서 문제를 처리했음을 나타냅니다.  이는 일부 분석 결과가 잘못되었을 수도 있음을 나타내는 경고입니다.  다른 반환 코드가 더 있는 경우에는 "어셈블리 참조 오류" 반환 코드를 오류로 간주해야 합니다.  
  
## 참고 항목  
 [코드 분석 응용 프로그램 오류](../code-quality/code-analysis-application-errors.md)