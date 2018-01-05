---
title: CV_CFL_LANG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CV_CFL_LANG enumeration
ms.assetid: 4e8e0613-ad02-4de9-9f46-e4753c5b0251
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 12dfcf493432116fcba36d55d1a85b977e9058b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cvcfllang"></a>CV_CFL_LANG
응용 프로그램이 나 연결 된 모듈의 소스 코드 언어를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
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
  
## <a name="elements"></a>요소  
 CV_CFL_C  
 응용 프로그램 언어는 C입니다.  
  
 CV_CFL_CXX  
 응용 프로그램 언어는 c + +입니다.  
  
 CV_CFL_FORTRAN  
 응용 프로그램 언어는 포트란입니다.  
  
 CV_CFL_MASM  
 응용 프로그램 언어는 Microsoft Macro Assembler입니다.  
  
 CV_CFL_PASCAL  
 응용 프로그램 언어는 파스칼식입니다.  
  
 CV_CFL_BASIC  
 응용 프로그램 언어 BASIC입니다.  
  
 CV_CFL_COBOL  
 응용 프로그램 언어는 COBOL입니다.  
  
 CV_CFL_LINK  
 응용 프로그램에는 링커 생성 모듈입니다.  
  
 CV_CFL_CVTRES  
 응용 프로그램은 리소스 모듈 CVTRES 도구와 함께 변환 합니다.  
  
 CV_CFL_CVTPGD  
 응용 프로그램은 CVTPGD 도구로 생성 된 액세스에 최적화 된 POGO 모듈.  
  
 CV_CFL_CSHARP  
 응용 프로그램 언어는 C#입니다.  
  
 CV_CFL_VB  
 응용 프로그램 언어에는 Visual Basic입니다.  
  
 CV_CFL_ILASM  
 응용 프로그램 언어에는 중간 언어 어셈블리 (즉, 공용 언어 런타임 (CLR) 어셈블리)입니다.  
  
 CV_CFL_JAVA  
 응용 프로그램 언어는 Java입니다.  
  
 CV_CFL_JSCRIPT  
 응용 프로그램 언어는 Jscript입니다.  
  
 CV_CFL_MSIL  
 응용 프로그램 언어는는 알 수 없는 언어 MSIL (Microsoft Intermediate)를 사용 하 여 결과 수는 [/LTCG (링크 타임 코드 생성)](/cpp/build/reference/ltcg-link-time-code-generation) 전환 합니다.  
  
 CV_CFL_HLSL  
 응용 프로그램 언어는 높은 수준의 셰이더 언어입니다.  
  
## <a name="remarks"></a>설명  
 이 열거형의 값에 대 한 호출에서 반환될지는 [idiasymbol:: Get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md) 메서드.  
  
## <a name="requirements"></a>요구 사항  
 헤더: cvconst.h  
  
## <a name="see-also"></a>참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_language](../../debugger/debug-interface-access/idiasymbol-get-language.md)