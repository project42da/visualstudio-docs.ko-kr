---
title: 프로파일링 도구 명령줄 도구의 경로 지정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8e25d5052cbc70e4a45040f8ebadb8cb36daa053
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/19/2018
---
# <a name="specifying-the-path-to-profiling-tools-command-line-tools"></a>프로파일링 도구 명령줄 도구의 경로 지정
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구 명령줄 도구의 경로가 PATH 환경 변수에 추가되지 않았습니다. 32비트 컴퓨터에는 도구가 단일 디렉터리에 있습니다. 64비트 컴퓨터에는 프로파일링 도구가 32비트 및 64비트 버전으로 있습니다.  
  
## <a name="32-bit-computers"></a>32비트 컴퓨터  
 32비트 컴퓨터에서 기본 프로파일러 도구가 위치한 디렉터리는 *드라이브*\Program Files\Microsoft Visual Studio 11.0\Team Tools\Performance Tools입니다.  
  
## <a name="64-bit-computers"></a>64비트 컴퓨터  
 64비트 컴퓨터에서 프로파일링된 응용 프로그램의 대상 플랫폼에 따라 경로를 지정합니다.  
  
-   32비트 응용 프로그램의 경우 기본 프로파일러 도구 디렉터리는 다음과 같습니다.  
  
     *드라이브*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools  
  
-   64비트 응용 프로그램의 경우 기본 프로파일러 도구가 위치한 디렉터리는 다음과 같습니다.  
  
     *드라이브*\Program Files (x86)\Microsoft Visual Studio 11.0\Team Tools\Performance Tools\x64