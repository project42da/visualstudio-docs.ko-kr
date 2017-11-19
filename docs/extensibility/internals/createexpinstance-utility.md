---
title: "CreateExpInstance 유틸리티 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- experimental builds
- experimental hive
- experimental instance
- createexpinstance
- createexpinst
ms.assetid: 03779774-9401-49ae-997c-0c3ab25ed0d5
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a90a5cfdc521de0716d81b07529822f69289b605
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="createexpinstance-utility"></a>CreateExpInstance 유틸리티
다시 설정, 만들려는 CreateExpInstance 유틸리티를 사용 하거나 Visual Studio의 실험적 인스턴스를 삭제 합니다. 디버깅 하 고 기본 제품을 변경 하지 않고 Visual Studio 확장을 테스트 실험적 인스턴스를 사용할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
CreateExpInstance.exe [/Create | /Reset | /Clean] /VSInstance=VsInstance /RootSuffix=Suffix  
```  
  
#### <a name="parameters"></a>매개 변수  
 / 만들기  
 실험적 인스턴스를 만듭니다.  
  
 / 다시 설정  
 실험적 인스턴스를 삭제 하 고 새 브러시를 만듭니다.  
  
 /Clean  
 실험적 인스턴스를 삭제합니다.  
  
 /Vsinstance  
 복사할 기본 Visual Studio 인스턴스를 포함 하는 디렉터리의 이름입니다.  
  
 /Rootsuffix  
 실험적 인스턴스 디렉터리의 이름에 추가할 접미사입니다.  
  
## <a name="remarks"></a>설명  
 Visual Studio 확장에서 작업 하는 경우 기본 실험적 인스턴스를 열고 현재 확장을 설치 하려면 f5 수 있습니다. 실험적 인스턴스를 사용할 수 있는 경우 Visual Studio가 기본 설정을 만듭니다.  
  
 실험적 인스턴스의 기본 위치는 Visual Studio 버전 번호에 따라 달라 집니다. 예를 들어 Visual Studio 2015에 대 한 위치가 %localappdata%\Microsoft\VisualStudio\14.0Exp\ 디렉터리 위치에 있는 모든 파일에는 해당 인스턴스의 일부로 간주 됩니다. 기본 위치에 디렉터리 이름을 변경 하지 않으면 Visual Studio에서 추가 실험적 인스턴스를 로드 하지 않습니다.  
  
 Visual Studio 실험적 인스턴스를 열었을 때 시스템 레지스트리를 액세스 하지 않습니다. 이전 버전의 Visual Studio는 실험 버전의 경우 레지스트리 하이브를 사용 하 여이 점에서 차이가 있습니다.  
  
 CreateExpInstance 유틸리티에서 VsRegEx 유틸리티가 대체합니다.  
  
 다음 예제에서는 Visual Studio의 기본 실험적 인스턴스 다시 설정합니다.  
  
 **CreateExpInstance.exe /Reset /VSInstance = 14.0 /RootSuffix = Exp**  
  
## <a name="see-also"></a>참고 항목  
 [VSPackage](../../extensibility/internals/vspackages.md)