---
title: "Vspackage를 등록 및 등록 취소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage 등록"
  - "Vspackage를 등록 하는 중"
ms.assetid: e25e7a46-6a55-4726-8def-ca316f553d6b
caps.latest.revision: 35
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 35
---
# Vspackage를 등록 및 등록 취소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

특성을 사용 하 여 VSPackage를 등록할 수 있지만  
  
## VSPackage를 등록 하는 중  
 관리 되는 VSPackages의 등록을 제어 하려면 특성을 사용할 수 있습니다. 모든 등록 정보는.pkgdef 파일에 포함 됩니다. 파일 기반 등록에 대 한 자세한 내용은 참조 하십시오. [CreatePkgDef 유틸리티](../extensibility/internals/createpkgdef-utility.md)합니다.  
  
 다음 코드에는 VSPackage를 등록 하는 표준 등록 특성을 사용 하는 방법을 보여 줍니다.  
  
```c#  
[PackageRegistration(UseManagedResourcesOnly = true)]  
[Guid("0B81D86C-0A85-4f30-9B26-DD2616447F95")]  
public sealed class BasicPackage : Package  
{. . .}  
```  
  
## 확장을 등록 취소  
 다른 Vspackage 많이 실험 진행 실험적 인스턴스를 제거 하려는 경우, 실행할 수 있습니다만 **재설정** 명령입니다. 찾아보십시오 **Visual Studio 실험적 인스턴스 다시 설정** 컴퓨터의 시작 페이지에서 또는 명령줄에서이 명령을 실행 합니다.  
  
```vb  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\CreateExpInstance.exe" /Reset /VSInstance=14.0 /RootSuffix=Exp  
```  
  
 로 이동 하는 사용자가 설치한 Visual Studio의 개발 인스턴스에서 확장을 제거 하려는 경우 **도구 \/ 확장 및 업데이트**, 확장명을 찾아서 클릭 **제거**합니다.  
  
 어떤 이유로 이러한 메서드의 모두 성공 하면에서 확장을 제거 하면 등록을 취소할 수 명령줄에서 VSPackage 어셈블리 다음과 같습니다.  
  
```  
<location of Visual Studio 2015 install>\"Microsoft Visual Studio 14.0\VSSDK\VisualStudioIntegration\Tools\Bin\regpkg” /unregister <pathToVSPackage assembly>  
```  
  
## 참고 항목  
 [Vspackage](../extensibility/internals/vspackages.md)