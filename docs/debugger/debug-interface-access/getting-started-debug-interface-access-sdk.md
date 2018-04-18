---
title: 시작 (디버그 인터페이스 액세스 SDK) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- .dbg files
- DBG files
ms.assetid: cb3d040a-2846-40d7-bdbc-8a5beb5dd2f6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d0c3c6df3fc92370d939771a7e94334db7f2cfc4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="getting-started-debug-interface-access-sdk"></a>시작(디버그 인터페이스 액세스 SDK)
디버그 인터페이스 액세스 (DIA) SDK 사용 안내 설명서와 DIA API를 사용 하는 방법을 보여 주는 샘플을 제공 합니다. DIA sdk에서는 인터페이스 및 메서드를 사용 하 여.pdb 및.dbg 파일을 열고 기호, 값, 특성, 주소 및 기타 디버깅 정보에 대 한 콘텐츠를 검색 하는 사용자 지정 응용 프로그램을 개발 하 합니다. 이 SDK는 또한 c + + 응용 프로그램에 있는 기호와 연결 된 속성에 대 한 참조 테이블을 제공 합니다.  
  
 DIA SDK를 최대한 활용 하려면 다음에 대해 잘 알고 있어야 합니다.  
  
-   C + + 프로그래밍 언어  
  
-   COM 프로그래밍  
  
-   Visual Studio 통합된 개발 환경 (IDE) 예제를 컴파일하기 위해  
  
 DIA SDK는 일반적으로 Visual Studio와 함께 설치 기본 위치는 *[드라이브]*files\microsoft Visual Studio 9.0\DIA SDK입니다. 설치의 일환으로, DIA SDK, 구현 하는 msdia90.dll는 자동으로 등록 하므로 사용 하기 위해 수행 해야을 포함 하는 `dia2.h` 프로그램 및 링크를 `diaguids.lib`합니다.  
  
 헤더: include\dia2.h  
  
 라이브러리: lib\diaguids.lib  
  
 DLL: bin\msdia80.dll  
  
 IDL: idl\dia2.idl  
  
## <a name="in-this-section"></a>섹션 내용  
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)  
 DIA.의 기본 아키텍처를 검토합니다.  
  
 [.Pdb 파일 쿼리](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)  
 .Pdb 파일을 쿼리할 DIA API를 사용 하는 방법에 대 한 단계별 지침을 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 인터페이스 액세스 SDK](../../debugger/debug-interface-access/debug-interface-access-sdk.md)