---
title: "출력에 대 한 프로젝트 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 구성, 출력"
ms.assetid: a4517f73-45af-4745-9d7f-9fddf887b636
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 출력에 대 한 프로젝트 구성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

모든 구성에는 출력 항목 예: 실행 파일 또는 리소스 파일을 생성 하는 빌드 프로세스 집합을 지원할 수 있습니다. 이러한 출력은 사용자의 전용 항목과 출력 실행 파일 \(.exe,.dll,.lib\) 및 소스 파일 \(.idl,.h 파일\) 등의 관련된 형식을 연결 하는 그룹에 배치할 수 있습니다.  
  
 출력 항목 수를 통해서만 사용할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput2> 메서드를 열거 하 고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumOutputs> 메서드. 출력 항목을 그룹화 하려는 경우 프로젝트 에서도 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputGroup> 인터페이스입니다.  
  
 구현 하 여 개발 된 구문을 `IVsOutputGroup` 사용량에 따라 그룹 출력에는 프로젝트 수 있도록 합니다. 예를 들어, DLL은 해당 프로그램 데이터베이스 \(PDB\)와 함께 그룹화 될 수 있습니다.  
  
> [!NOTE]
>  디버깅 정보를 포함 하는 PDB 파일 및.dll 또는.exe를 빌드할 때 ' 디버그 정보 생성 ' 옵션을 지정 하면 만들어집니다. .Pdb 파일은 일반적으로 디버그 프로젝트 구성만 생성 됩니다.  
  
 프로젝트 그룹 내에 포함 된 출력 수 구성을 구성 달라질 것도 그룹을 지 원하는 각 구성에 대해 동일한 수를 반환 해야 합니다. 예를 들어 프로젝트 Matt의 DLL mattd.dll와 mattd.pdb 디버그 구성에 포함 되지만 matt.dll 소매 구성에 포함 될 수 있습니다.  
  
 그룹 수도 정식 이름, 표시 이름 및 그룹 정보 같은 동일한 식별자 정보 구성에서 구성 프로젝트 내에서. 이 일관성 배포 및 패키지 계속 구성을 변경 하는 경우에 작동할 수 있습니다.  
  
 그룹에 의미 있는 가리키도록 패키징 바로 가기를 수 있는 키 출력이 있을 수도 있습니다. 그룹의 크기에 대 한 어떠한가 정도 하지를 만들어야 하므로 모든 그룹에 지정된 된 구성 비어 있을 수 있습니다. 모든 구성에서 각 그룹의 크기 \(출력 수\)는 동일한 구성에 다른 그룹의 크기와에서 다를 수 있습니다. 또한 다른 구성에서 동일한 그룹의 크기와에서 다른 수 있습니다.  
  
 ![출력 그룹 그래픽](~/docs/extensibility/internals/media/vsoutputgroups.gif "vsOutputGroups")  
출력 그룹  
  
 주된 용도 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg> 인터페이스 빌드, 배포 및 관리 개체의 디버깅 및 허용 프로젝트 출력 그룹에 자유에 대 한 액세스를 제공 하는 것입니다. 이 인터페이스의 사용에 자세한 내용은 참조 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)합니다.  
  
 이전 다이어그램에서 그룹 작성에 키가 있으므로 \(bD.exe 또는 b.exe\) 구성에 따른 출력 내장 바로 가기를 만들을 바로 가기를 배포 구성에 관계 없이 작동 하는지 알 수 있습니다. 그룹 원본 없으므로 출력에 키를 사용자에 대 한 바로 가기를 만들 수 없습니다. 출력을 키가 디버그 그룹 작성 하는 경우 없는 소매 그룹 작성 구현이 잘못 될 것입니다. 그런 다음, 하는 구성이 없는 출력을 포함 하는 그룹에 있고, 결과적으로, 키 파일이 없는 다음 해당 그룹과 않는 출력을 포함 하는 다른 구성 없습니다 키 파일. 설치 관리자 편집기 가정 정식 이름 및 키 파일의 존재 여부와 그룹의 표시 이름을 변경 하지 마십시오 구성에 기반 합니다.  
  
 경우에 프로젝트에는 `IVsOutputGroup` 는 되지 않게 하려면 배포 또는 패키지를 그룹에 해당 출력을 포함 하지 않기 위해 충분있지 않습니다. 출력 여전히 열거할 수 일반적으로 구현 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg.EnumOutputs%2A> 모든 그룹화에 관계 없이 구성의 출력을 반환 하는 메서드입니다.  
  
 자세한 내용은 참조 구현 `IVsOutputGroup` 에서 사용자 지정 프로젝트 샘플에 [프로젝트의 MPF](http://mpfproj12.codeplex.com)합니다.  
  
## 참고 항목  
 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)   
 [빌드를 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)   
 [솔루션 구성](../../extensibility/internals/solution-configuration.md)