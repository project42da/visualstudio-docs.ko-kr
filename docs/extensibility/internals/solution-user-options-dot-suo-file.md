---
title: 솔루션 사용자 옵션 (합니다. Suo) 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- .suo files, VSPackages
- suo files, VSPackages
- solutions, .suo files
- solutions, user options
- solution user options (.suo) file
ms.assetid: 75258e0d-600d-4a3d-94f4-3d7ac12cb47c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 0b96e3ad2ec29402dddc7354df46293b99bac3ec
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="solution-user-options-suo-file"></a>솔루션 사용자 옵션 (합니다. Suo) 파일
솔루션 사용자 옵션 (.suo) 파일에는 사용자 단위 솔루션 옵션 포함 되어 있습니다. 이 파일 소스 코드 제어에 체크 하지 않아야 합니다.  
  
 솔루션 사용자 옵션 (.suo) 파일은 구조적된 저장소 또는 복합, 이진 형식으로 저장 된 파일. .Suo 파일에 정보를 식별 하는 키가 아닌 스트림의 이름을 가진 스트림으로 사용자 정보를 저장 합니다. 솔루션 사용자 옵션 파일 사용자 기본 설정을 저장 하는 데 사용 되 고 Visual Studio는 솔루션을 저장 하는 경우 자동으로 생성 됩니다.  
  
 환경.suo 파일을 열면 현재 로드 된 Vspackage를 모두 열거 합니다. VSPackage 구현 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> 인터페이스를 다음 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.LoadUserOptions%2A> .suo 파일에서 모든 데이터를 로드 하려면 요청한 VSPackage에서 메서드.  
  
 되기 스트리밍하 무엇을 알아야 VSPackage의 책임.suo 파일에 기록 수 있습니다. 쓰게 각 스트림에 대 VSPackage를 다시 호출을 통해 환경 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> 스트림의 이름을 키로 식별 되는 특정 스트림을 로드 합니다. 환경을 다음 콜백 하는 스트림의 이름을 전달 하는 특정 스트림을 읽는 데 VSPackage 및 `IStream` 에 대 한 포인터는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> 메서드.  
  
 해당 시점에 다른 호출 `LoadUserOptions` 를 읽을 수 있는.suo 파일의 다른 섹션 있는지 확인 합니다. 이 프로세스에는 모든.suo 파일에 데이터 스트림 읽기 되어 환경에서 처리 될 때까지 계속 됩니다.  
  
 솔루션이 저장 되거나 닫힌 경우 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.SavePackageSolutionProps%2A> 완벽 하 게 메서드는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.SaveUserOptions%2A> 메서드. `IStream` 에 전달 되는 이진 정보를 저장할 수를 포함 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.WriteUserOptions%2A> 메서드.suo 파일 및 호출 정보를 기록 합니다는 `SaveUserOptions` 다른 스트림에의 정보는.suo에 쓸 수 있는지 확인 하려면 다시 메서드 파일입니다.  
  
 이 두 방법 `SaveUserOptions` 및 `WriteUserOptions`에 대 한 포인터를 전달.suo 파일에 저장 되는 정보의 각 스트림에 대해 재귀적으로 호출 된 `IVsSolutionPersistence`합니다. 여러 스트림.suo 파일에 쓰기를 허용 하도록 재귀적으로 호출 됩니다. 이러한 방법으로 사용자 정보 솔루션과 함께 유지 되 고에 솔루션이 열려 있을 보장 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 [솔루션](../../extensibility/internals/solutions.md)