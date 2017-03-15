---
title: "CV_CFL_LANG | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CV_CFL_LANG 열거형"
ms.assetid: 4e8e0613-ad02-4de9-9f46-e4753c5b0251
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# CV_CFL_LANG
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

응용 프로그램 또는 연결된 모듈의 소스 코드 언어를 지정합니다.  
  
## 구문  
  
```cpp#  
typedef enum CV_CFL_LANG {   
   CV_CFL_C       = 0x00,  
   CV_CFL_CXX     = 0x01,  
   CV_CFL_FORTRAN = 0x02,  
   CV_CFL_MASM    = 0x03,  
   CV_CFL_PASCAL  = 0x04,  
   CV_CFL_BASIC   = 0x05,  
   CV_CFL_COBOL   = 0x06,  
   CV_CFL_LINK    = 0x07,  
   CV_CFL_CVTRES  = 0x08,  
   CV_CFL_CVTPGD  = 0x09,  
   CV_CFL_CSHARP  = 0x0A,  
   CV_CFL_VB      = 0x0B,  
   CV_CFL_ILASM   = 0x0C,  
   CV_CFL_JAVA    = 0x0D,  
   CV_CFL_JSCRIPT = 0x0E,  
   CV_CFL_MSIL    = 0x0F,  
   CV_CFL_HLSL    = 0x10  
} CV_CFL_LANG;  
```  
  
## Elements  
 CV\_CFL\_C  
 응용 프로그램 언어는 C입니다.  
  
 CV\_CFL\_CXX  
 응용 프로그램 언어는 C\+\+입니다.  
  
 CV\_CFL\_FORTRAN  
 포트란 언어 응용 프로그램을 것입니다.  
  
 CV\_CFL\_MASM  
 Microsoft 매크로 어셈블러 언어 응용 프로그램을 것입니다.  
  
 CV\_CFL\_PASCAL  
 응용 프로그램 언어 파스칼입니다.  
  
 CV\_CFL\_BASIC  
 응용 프로그램 언어 기본입니다.  
  
 CV\_CFL\_COBOL  
 응용 프로그램 언어 COBOL입니다.  
  
 CV\_CFL\_LINK  
 응용 프로그램에는 링커 생성 모듈입니다.  
  
 CV\_CFL\_CVTRES  
 응용 프로그램 리소스 CVTRES 도구로 변환 모듈입니다.  
  
 CV\_CFL\_CVTPGD  
 응용 프로그램 CVTPGD 도구로 생성 POGO 최적화 된 모듈입니다.  
  
 CV\_CFL\_CSHARP  
 응용 프로그램 언어는 C\#입니다.  
  
 CV\_CFL\_VB  
 응용 프로그램 언어는 Visual Basic입니다.  
  
 CV\_CFL\_ILASM  
 응용 프로그램 언어 il 어셈블리 \(즉, CLR \(공용 언어 런타임\) 어셈블리\)입니다.  
  
 CV\_CFL\_JAVA  
 응용 프로그램 언어는 Java입니다.  
  
 CV\_CFL\_JSCRIPT  
 응용 프로그램 언어에는 Jscript입니다.  
  
 CV\_CFL\_MSIL  
 응용 프로그램 언어 되는 알 수 없는 Microsoft 중간 언어 \(MSIL\), 사용 가능한 경우 결과 [\/LTCG\(링크 타임 코드 생성\)](/visual-cpp/build/reference/ltcg-link-time-code-generation) 전환 합니다.  
  
 CV\_CFL\_HLSL  
 응용 프로그램 언어 높은 수준 셰이더 언어입니다.  
  
## 설명  
 이 열거형의 값은 [IDiaSymbol::get\_language](../../debugger/debug-interface-access/idiasymbol-get-language.md) 메서드 호출에 의해 반환됩니다.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get\_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)