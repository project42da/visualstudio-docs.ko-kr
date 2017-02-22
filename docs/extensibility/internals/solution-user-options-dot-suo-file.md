---
title: "솔루션 사용자 옵션 (합니다. Suo) 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage.suo 파일"
  - "Vspackage suo 파일"
  - "솔루션,.suo 파일"
  - "솔루션 사용자 옵션"
  - "솔루션 사용자 옵션 파일 (.suo)"
ms.assetid: 75258e0d-600d-4a3d-94f4-3d7ac12cb47c
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 솔루션 사용자 옵션 (합니다. Suo) 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

솔루션 사용자 옵션 \(.suo\) 파일 사용자별 솔루션 옵션을 포함합니다. 이 파일 소스 코드 제어에 체크 하지 않아야 합니다.  
  
 솔루션 사용자 옵션 \(.suo\) 파일은 구조적된 저장소 또는 복합, 이진 형식으로 저장 된 파일. .Suo 파일에 대 한 정보를 식별 하는 데 사용 될는 키가 아닌 스트림 이름의 스트림으로 사용자 정보를 저장 합니다. 솔루션 사용자 옵션 파일 사용자 기본 설정을 저장 하는 데 사용 되 고 Visual Studio 솔루션을 저장할 때 자동으로 만들어집니다.  
  
 환경.suo 파일을 열면 모든 현재 로드 된 Vspackage를 열거 합니다. VSPackage를 구현 하는 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> 인터페이스에 다음 호출 하 여 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.LoadUserOptions%2A> .suo 파일의 모든 데이터를 로드 하려면 요청 VSPackage에서 메서드.  
  
 VSPackage의 책임 스트리밍할 무엇을 알아야.suo 파일에 작성할 수 있습니다. 쓰게 각 스트림에 대해 VSPackage를 다시 호출을 통해 환경 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> 스트림의 이름을 키로 식별 되는 특정 스트림을 로드 합니다. 환경을 호출 하면 다시 스트림의 이름을 전달 하는 특정 스트림을 읽는 데 VSPackage 및 `IStream` 에 대 한 포인터는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.LoadPackageUserOpts%2A> 메서드.  
  
 이 시점에서 다른 호출 `LoadUserOptions` 읽을 수 있는.suo 파일의 다른 섹션 있는지 확인 합니다. 이 프로세스는.suo 파일에 데이터 스트림의 모든 읽기 및 된 환경에 의해 처리 될 때까지 계속 됩니다.  
  
 솔루션 저장 되거나 닫힌 경우 환경 호출의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence.SavePackageSolutionProps%2A> 메서드에 대 한 포인터는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.SaveUserOptions%2A> 메서드.`IStream` 에 전달 되는 저장할 이진 정보를 포함 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts.WriteUserOptions%2A> .suo 파일을 호출 정보를 기록 합니다 메서드는 `SaveUserOptions` 메서드.suo 파일에 쓸 수 있는 정보의 다른 스트림을 인지를 다시 합니다.  
  
 이 두 방법 `SaveUserOptions` 및 `WriteUserOptions`, 에 대 한 포인터를 전달 하는.suo 파일에 저장 되는 정보의 각 스트림에 대해 재귀적으로 호출 됩니다 `IVsSolutionPersistence`합니다. 여러 스트림.suo 파일에 기록 하는 작업에 대 한 허용에 재귀적으로 호출 됩니다. 이러한 방법으로 사용자 정보 솔루션 함께 유지 되며 다음에 솔루션이 열려 있을 보장 됩니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 [솔루션](../../extensibility/internals/solutions.md)