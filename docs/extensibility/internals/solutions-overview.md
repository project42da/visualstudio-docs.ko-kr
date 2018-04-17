---
title: 솔루션 개요 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- solutions, about solutions
ms.assetid: 3b21e3a1-170a-4485-941e-6b04b7b27886
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d64175c570c4fbca26bae0aa587b66e04cbee2be
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="solutions-overview"></a>솔루션 개요
솔루션은 응용 프로그램을 만드는 함께 작동 하는 하나 이상의 프로젝트를 그룹화 합니다. 솔루션에 대 한 프로젝트 및 상태 정보는 두 개의 서로 다른 솔루션 파일에 저장 됩니다. 솔루션 (.sln) 파일은 텍스트 기반 소스 코드 제어에서 사용 중인 및 사용자 간에 공유 될 수 있습니다. 솔루션 사용자 옵션 (.suo) 파일은 binary입니다. 결과적으로,.suo 파일 소스 코드 제어에서 사용할 수 없습니다 및 사용자 관련 정보를 포함 합니다.  
  
 모든 VSPackage 솔루션 파일 유형에 쓸 수 있습니다. 파일에서는 이기 때문에 두 가지 다른 인터페이스 구현에 쓸 수 있습니다. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> .sln 파일을 텍스트 정보를 기록 하는 인터페이스 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> 인터페이스 이진 스트림을.suo 파일에 씁니다.  
  
> [!NOTE]
>  프로젝트는 솔루션 파일로 자체에 대 한 항목을 명시적으로 쓸 필요가 없습니다. 환경을 처리 하는 프로젝트에 대 한 합니다. 따라서 내용을 더 구체적으로 솔루션 파일에 추가 하려는 경우가 아니면 않아도를 이러한 방식으로 VSPackage를 등록 합니다.  
  
 세 개의 인터페이스를 사용 하는 솔루션 지 속성을 지 원하는 각 VSPackage는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> 인터페이스에는 환경에서 구현 하 고는 VSPackage에서 호출 되 면 및 `IVsPersistSolutionProps` 및 `IVsPersistSolutionOpts`는 VSPackage에서 둘 다 구현 하는 합니다. `IVsPersistSolutionOpts` 인터페이스만 개인 정보를.suo 파일에는 VSPackage에서 기록 하는 경우에 구현 해야 합니다.  
  
 솔루션을 열 때 다음 프로세스가 수행이 됩니다.  
  
1.  환경에서 솔루션을 읽습니다.  
  
2.  환경을 찾으면는 `CLSID`, 해당 VSPackage를 로드 합니다.  
  
3.  경우 VSPackage 로드 되는 환경 호출 `QueryInterface` 에 대 한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> VSPackage 필요로 하는 인터페이스에 대 한 인터페이스입니다.  
  
    1.  환경 호출.sln 파일을 읽을 때 `QueryInterface` 에 대 한 `IVsPersistSolutionProps`합니다.  
  
    2.  환경 호출.suo 파일을 읽을 때 `QueryInterface` 에 대 한 `IVsPersistSolutionOpts`합니다.  
  
 이러한 파일의 사용에 관련 된 특정 정보를 확인할 수 있습니다 [솔루션 (합니다. Sln) 파일](../../extensibility/internals/solution-dot-sln-file.md) 및 [솔루션 사용자 옵션 (합니다. Suo) 파일](../../extensibility/internals/solution-user-options-dot-suo-file.md)합니다.  
  
> [!NOTE]
>  세 번째 빌드에서 제외 하 고 두 프로젝트 구성으로 구성 된 새 솔루션 구성을 하려는 경우 속성 페이지 UI 또는 자동화를 사용 해야 합니다. 솔루션 빌드 관리자 구성 및 해당 속성은 직접 변경할 수 없지만 솔루션 빌드 관리자를 사용 하 여 조작할 수 있습니다는 `SolutionBuild` DTE 자동화 모델에서 클래스입니다. 솔루션을 구성 하는 방법에 대 한 자세한 내용은 참조 [솔루션 구성](../../extensibility/internals/solution-configuration.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>