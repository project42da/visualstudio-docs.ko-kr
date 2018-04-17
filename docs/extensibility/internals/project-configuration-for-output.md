---
title: 프로젝트 출력에 대 한 구성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project configurations, output
ms.assetid: a4517f73-45af-4745-9d7f-9fddf887b636
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d9bb68812ed9988c9ed18174231ead24f91fcf9d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="project-configuration-for-output"></a>출력에 대 한 프로젝트 구성
모든 구성에는 실행 파일 또는 리소스 파일 등의 출력 항목을 생성 하는 빌드 프로세스의 집합을 지원할 수 있습니다. 이러한 출력은 사용자의 전용 항목과 출력 실행 파일 (.exe,.dll,.lib) 및 소스 파일 (.idl,.h 파일) 등의 관련된 형식을 연결 하는 그룹에 배치할 수 있습니다.  
  
 출력 항목을 통해 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2> 메서드를 열거 하 고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs> 메서드. 출력 항목을 그룹화 하려는 경우 프로젝트 에서도 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup> 인터페이스입니다.  
  
 구현 하 여 개발 된 구문이 `IVsOutputGroup` 프로젝트 사용에 따라 출력 그룹에 있습니다. 예를 들어, DLL 프로그램 데이터베이스 (PDB)와 그룹화 될 수 있습니다.  
  
> [!NOTE]
>  PDB 파일에 디버깅 정보가 및.dll 또는.exe를 작성할 때 ' 디버그 정보 생성 ' 옵션을 지정 하면 생성 됩니다. .Pdb 파일은 일반적으로 디버그 프로젝트 구성만에 대해 생성 됩니다.  
  
 그룹 내에 포함 된 출력 수 구성 구성에서 다를 수 있습니다 하는 경우에 프로젝트 그룹을 지 원하는 각 구성에 대해 동일한 수를 반환 해야 합니다. 예를 들어 프로젝트 Matt의 DLL mattd.dll와 mattd.pdb 디버그 구성에 포함 하지만 matt.dll 소매 구성에 포함 될 수 있습니다.  
  
 그룹 레이블에도 정식 이름, 표시 이름 및 그룹 정보 같은 동일한 식별자 정보 구성에서 구성 프로젝트 내에서. 이 일관성을 통해 배포 및 구성을 변경 하는 경우에 작업을 계속 하려면는 패키지입니다.  
  
 그룹에 의미 있는를 가리키도록 패키징 바로 가기 키를 허용 하는 키 출력이 있을 수도 있습니다. 그룹의 크기에 대 한 어떠한가 정도 하지 만들어야 하므로 모든 그룹에 지정된 된 구성 비어 있을 수 있습니다. 구성에서 각 그룹의 크기 (출력 수)는 동일한 구성에 다른 그룹의 크기와에서 다를 수 있습니다. 또한 다른 구성에서 동일한 그룹의 크기와에서 다를 수 있습니다.  
  
 ![출력 그룹 그래픽](../../extensibility/internals/media/vsoutputgroups.gif "vsOutputGroups")  
출력 그룹  
  
 주된 용도 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg> 인터페이스 빌드, 배포 및 관리 개체의 디버깅 및 허용 프로젝트 출력 그룹에 자유에 대 한 액세스를 제공 하는 것입니다. 이 인터페이스의 사용에 자세한 내용은 참조 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)합니다.  
  
 이전 다이어그램에 그룹 작성에 키가 있으므로 (bD.exe 또는 b.exe) 구성에 따른 출력 사용자 내장 바로 가기를 만들 수 있으며 배포 된 구성에 관계 없이 바로 가기가 작동 하는지 확인 합니다. 그룹 소스는 없으므로 출력으로 키를 사용자는 바로 가기를 만들 수 없습니다. 키 출력에 디버그 그룹 작성 하지 않는 소매 그룹 작성 표시 되지만 잘못 구현 될 것입니다. 그런 다음에, 하는 구성이 없는 출력을 포함 하는 그룹에 있고, 결과적으로, 없습니다 키 파일을 다음 출력 포함 해당 그룹에 다른 구성을 수 없습니다 키 파일. 설치 관리자 편집기 가정 정식 이름 및 키 파일의 존재 여부와 그룹의 표시 이름을 변경 하지 마십시오 구성에 기반 합니다.  
  
 경우에 프로젝트에는 `IVsOutputGroup` 는 되지 않게 하려면 패키지를 배포 하거나, 그룹에 해당 출력을 삽입 하지 해도 되 합니다. 출력을 구현 하 여 정상적으로 열거 여전히 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg.EnumOutputs%2A> 모든 그룹화에 관계 없이 구성의 출력을 반환 하는 메서드입니다.  
  
 참조의 구현에 대 한 자세한 내용은 `IVsOutputGroup` 에서 사용자 지정 프로젝트 샘플 [프로젝트의 MPF](http://mpfproj12.codeplex.com)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [구성 옵션을 관리](../../extensibility/internals/managing-configuration-options.md)   
 [만들기에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)   
 [솔루션 구성](../../extensibility/internals/solution-configuration.md)