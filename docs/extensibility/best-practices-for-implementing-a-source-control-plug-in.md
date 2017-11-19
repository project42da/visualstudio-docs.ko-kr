---
title: "소스 제어 플러그 인을 구현 하기 위한 모범 사례 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control plug-ins, best practices
- best practices, source control plug-ins
- source control [Visual Studio SDK], plug-ins
ms.assetid: 85e73b73-29dc-464f-8734-ed308742c435
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9099d652012fb8b45b7b79f9c620f4102e7af602
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="best-practices-for-implementing-a-source-control-plug-in"></a>소스 제어 플러그 인을 구현 하기 위한 모범 사례
다음 기술 세부 정보 수 안정적으로 구현할 수는 소스 제어 플러그 인에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="memory-management-issues"></a>메모리 관리 문제  
 대부분의 경우 호출자에 게는 통합된 개발 환경 (IDE)를 해제 하 고 메모리를 할당 합니다. 소스 제어 플러그 인 호출자 할당 버퍼에 문자열 및 기타 항목을 반환합니다. 예외가 발생 하는 특정 함수에 대 한 설명에 명시 되어 있습니다.  
  
## <a name="arrays-of-file-names"></a>파일 이름 배열  
 파일 배열에 전달 되 면 파일 이름의 연속적인 배열로 전달 되지 않습니다. 파일 이름에 대 한 포인터의 배열로 전달 됩니다. 예를 들어는 [SccGet](../extensibility/sccget-function.md), 파일 이름에 의해 전달 됩니다는 `lpFileNames` 매개 변수를 여기서 `lpFileNames` 실제로에 대 한 포인터는 `char **`합니다. `lpFileNames`[0] first name에 대 한 포인터 `lpFileNames`[1] 두 번째 이름 등에 대 한 포인터입니다.  
  
## <a name="large-model"></a>큰 모델  
 모든 포인터는 16 비트 운영 체제에 32 비트입니다.  
  
## <a name="fully-qualified-paths"></a>정규화 된 경로  
 여기서 파일 이름 또는 디렉터리가 인수로 지정 된 정규화 된 경로 또는 끝 백슬래시 없이 UNC 경로 여야 합니다. 이 경우 기본 원본 제어 시스템의 요구 사항 즉 상대 경로를 변환 하는 플러그 인 소스 제어의 작업은  
  
## <a name="specify-a-fully-qualified-path-for-the-registered-dll"></a>등록 된 DLL에 대 한 정규화 된 경로 지정 합니다.  
 IDE는 더 이상 상대 경로 (예를 들어.\NewProvider.dll)에서 Dll을 로드합니다. DLL의 전체 경로 (예: C:\Providers\NewProvider.dll) 지정 해야 합니다. 이 요구 사항은 무단 또는 가장 된 소스 제어 Dll 로드할 수 없도록 하 여 IDE의 보안을 강화 합니다.  
  
## <a name="check-for-an-existing-vssci-plug-in-when-you-install-your-source-control-plug-in"></a>기존 VSSCI 소스 제어 플러그 인을 설치할 때 플러그 인에 대 한 확인  
 소스 제어 플러그 인을 설치 하려는 사용자는 기존 소스 제어 플러그 인 컴퓨터에 설치를 이미 있을 수 있습니다. (설치) 설치 프로그램은 플러그 인에 대 한 만드는 결정 해야 관련 레지스트리 키에 대 한 기존 값이 있는지 여부. 이러한 키는 이미 설정 된 경우 설치 프로그램에 게 문의 해야 사용자 기본 소스 제어 플러그 인으로 플러그 인을 등록 하 여 이미 설치 되어 있는 바꿀 것인지 여부입니다.  
  
## <a name="error-result-codes-and-reporting"></a>오류 결과 코드 및 보고  
 `SCC_OK` 반환 코드를 소스 제어 기능에 대 한 모든 파일에 대 한 작업이 성공 했다는 것을 나타냅니다. 작업이 실패 하면 발생 한 마지막 오류 코드를 반환할 사용할 수 있습니다.  
  
 보고에 대 한 규칙은 IDE에서 오류가 발생 하는 경우 IDE는 보고 하는 일을 담당 합니다. 소스 제어 시스템에서 오류가 발생 하는 경우 소스 제어 플러그 인는 보고 하는 일을 담당 합니다. 예를 들어, "파일이 현재 선택 된" 보고 되는 IDE에 의해 반면 "이이 파일은 이미 체크 아웃 됨"이 플러그 인에서 보고 됩니다.  
  
## <a name="the-context-structure"></a>상황에 맞는 구조  
 호출 하는 동안는 [SccInitialize](../extensibility/sccinitialize-function.md), 호출자에 게 전달 된 `ppvContext` 매개 변수는 초기화 되지 않은 핸들에는 void 인 합니다. 소스 제어 플러그 인이 매개 변수를 무시할 수 또는 어떤 종류의 구조를 할당 하 고 해당 구조에 대 한 포인터를 전달 된 포인터 넣을 수 있습니다. IDE는이 구조를 인식 하지 못하는 있지만 플러그 인에서 다른 모든 호출에이 구조에 대 한 포인터를 전달 하기. 전역 변수를 사용 하지 않고 함수 호출에서 지속 되는 전역 상태 정보를 유지 하는 데 사용할 수 있는 플러그 인에 중요 한 상황에 맞는 캐시 정보를 제공 합니다. 플러그 인에 대 한 책임이 해제에 대 한 호출에서 구조는 [SccUninitialize](../extensibility/sccuninitialize-function.md)합니다.  
  
 경우 플러그 인 설정은 `SCC_CAP_REENTRANT` 비트는 [SccInitialize](../extensibility/sccinitialize-function.md) (구체적으로 `lpSccCaps` 매개 변수), 여러 컨텍스트 구조는 열려 있는 모든 프로젝트를 추적 하는 데 합니다.  
  
## <a name="bitflags-and-other-command-options"></a>비트 및 기타 명령 옵션  
 각 명령에 대해 같은 [SccGet](../extensibility/sccget-function.md), IDE는 명령의 동작을 변경 하는 다양 한 옵션을 지정할 수 있습니다.  
  
 API를 통해 IDE에 의해 특정 옵션 설정을 지원는 `fOptions` 매개 변수입니다. 이러한 옵션은 [에서 특정 명령을 사용 하는 비트](../extensibility/bitflags-used-by-specific-commands.md) 함께 명령에 영향을 줍니다. 일반적으로 다음은을 사용자 하지 여부 옵션입니다.  
  
 사용자 구성 가능한 설정 옵션에 가장 크게 다르므로 소스 제어 플러그 인에서 이런 방식으로 정의 되지 않습니다. 따라서 권장 되는 메커니즘은는 **고급** 단추입니다. 예를 들어,는 **가져오기** 대화 상자, IDE 이해 하기 하기는 하지만 또한 표시 된 정보만 표시 됩니다는 **고급** 플러그 인에이 명령에 대 한 옵션 단추입니다. 사용자가 클릭할 때는 **고급** 단추를 호출 하 여 IDE는 [SccGetCommandOptions](../extensibility/sccgetcommandoptions-function.md) 소스 제어 플러그 비트 또는 날짜/시간 등의 정보에 대 한 사용자를 요청할 수 있도록 합니다. 플러그 인 실행 중에 다시 전달 되는 구조에이 정보를 반환 된 `SccGet` 명령입니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인](../extensibility/source-control-plug-ins.md)   
 [소스 제어 플러그 인 만들기](../extensibility/internals/creating-a-source-control-plug-in.md)