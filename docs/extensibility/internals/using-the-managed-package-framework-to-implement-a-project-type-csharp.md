---
title: "프로젝트 형식 (C#)에 대 한 관리 되는 패키지 프레임 워크를 사용 하 여 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], creating with MPF
- MPF projects
- managed package framework, creating projects
ms.assetid: 926de536-eead-415b-9451-f1ddc8c44630
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d5bc147592bfc36247c35f23ac2885055d096af3
ms.openlocfilehash: 1d70a70b942b3722ed61e1e8a2f2e54d96b916e4
ms.lasthandoff: 02/22/2017

---
# <a name="using-the-managed-package-framework-to-implement-a-project-type-c"></a>프로젝트 형식 (C#)를 구현 하는 관리 되는 패키지 프레임 워크를 사용 하 여
관리 되는 패키지 프레임 워크 (MPF)는 C# 클래스를 사용 하거나 사용자 고유의 프로젝트 형식을 구현 하에서 상속 하는 수를 제공 합니다. MPF 자체 프로젝트 형식의 특정 구현에 주력할 남게 여러 가지 Visual Studio를 제공 하기 위해 프로젝트 형식에서는 인터페이스를 구현 합니다.  
  
## <a name="using-the-mpf-project-source-code"></a>MPF 프로젝트 소스 코드를 사용 하 여  
 프로젝트 (MPFProj)에 대 한 관리 되는 패키지 프레임 워크는 만들고 새로운 프로젝트 시스템을 관리 하기 위한 도우미 클래스를 제공 합니다. 프로젝트 클래스 MPF에서 다른 클래스와는 달리 Visual Studio와 함께 제공 되는 어셈블리에 포함 되지 않습니다. 프로젝트 클래스는 소스 코드에서로 제공 되는 대신, [프로젝트 2013 MPF](http://mpfproj12.codeplex.com)합니다.  
  
 이 프로젝트를 VSPackage 솔루션을 추가 하려면 다음을 수행 합니다.  
  
1.  MPFProj 파일을 다운로드 *MPFProjectDir*합니다.  
  
2.  에 *MPFProjectDir*\Dev10\Src\CSharp\ProjectBase.file, 다음 블록을 변경 합니다.  
  
```  
<!-- Provide a default value for $(ProjectBasePath) -->  
  <PropertyGroup>  
    <ProjectBasePath >MPFProjDir\Dev10\Src\CSharp</ProjectBasePath>  
  </PropertyGroup>  
```  
  
1.  VSPackage 프로젝트를 만듭니다.  
  
2.  VSPackage 프로젝트를 업로드 합니다.  
  
3.  다른 하기 전에 다음 블록을 추가 하 여 VSPackage.csproj 파일을 편집 `<Import>` 블록:  
  
```  
<Import Project="MPFProjectDir\Dev10\Src\CSharp\ProjectBase.files" />  
  <PropertyGroup>  
    <!--To specify a different registry root to register your package, uncomment the TargetRegistryRoot tag and specify a registry root in it.  
    <TargetRegistryRoot></TargetRegistryRoot>-->  
    <RegisterOutputPackage>true</RegisterOutputPackage>  
    <RegisterWithCodebase>true</RegisterWithCodebase>  
  </PropertyGroup>  
```  
  
1.  프로젝트를 저장합니다.  
  
2.  VSPackage 솔루션을 닫았다가 설정 합니다.  
  
3.  VSPackage 프로젝트를 다시 엽니다. ProjectBase 라는 새 디렉터리에 표시 됩니다.  
  
4.  VSPackage 프로젝트에 다음 참조를 추가 합니다.  
  
     Microsoft.Build.Tasks.4.0  
  
5.  프로젝트를 빌드합니다.  
  
## <a name="hierarchy-classes"></a>클래스 계층 구조  
 다음 표에서 프로젝트 계층 구조를 지원 하 고 MPFProj의 클래스를 보여 줍니다. 자세한 내용은 참조 [계층 구조 및 선택](../../extensibility/internals/hierarchies-and-selection.md)합니다.  
  
|클래스 이름|  
|----------------|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|  
|`Microsoft.VisualStudio.Package.ProjectNode`|  
|`Microsoft.VisualStudio.Package.ProjectContainerNode`|  
|`Microsoft.VisualStudio.Package.FileNode`|  
|`Microsoft.VisualStudio.Package.FolderNode`|  
|`Microsoft.VisualStudio.Package.ReferenceContainerNode`|  
|`Microsoft.VisualStudio.Package.ReferenceNode`|  
|`Microsoft.VisualStudio.Package.ProjectReferenceNode`|  
|`Microsoft.VisualStudio.Package.ComReferenceNode`|  
|`Microsoft.VisualStudio.Package.AssemblyReferenceNode`|  
|`Microsoft.VisualStudio.Package.BuildDependency`|  
  
## <a name="document-handling-classes"></a>문서 처리 클래스  
 다음 표에서 문서 처리를 지 MPF의 클래스를 나열 합니다. 자세한 내용은 참조 [열기 및 프로젝트 항목 저장](../../extensibility/internals/opening-and-saving-project-items.md)합니다.  
  
|클래스 이름|  
|----------------|  
|`Microsoft.VisualStudio.Package.DocumentManager`|  
|`Microsoft.VisualStudio.Package.FileDocumentManager`|  
  
## <a name="configuration-and-output-classes"></a>구성 및 출력 클래스  
 다음 표에서 디버그 및 릴리스 및 프로젝트 출력 컬렉션 등의 여러 구성을 지 원하는 프로젝트 형식 수 있게 해 주는 MPF의 클래스를 나열 합니다. 자세한 내용은 참조 [관리 구성 옵션](../../extensibility/internals/managing-configuration-options.md)합니다.  
  
|클래스 이름|  
|----------------|  
|`Microsoft.VisualStudio.Package.ConfigProvider`|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|  
|`Microsoft.VisualStudio.Package.BuildableProjectConfig`|  
|`Microsoft.VisualStudio.Package.OutputGroup`|  
|`Microsoft.VisualStudio.Package.ProjectElement`|  
  
## <a name="automation-support-classes"></a>자동화 지원 클래스  
 다음 표에서 자동화를 지 원하는 프로젝트 형식의 사용자가 추가 기능을 작성할 수 있도록 MPF의 클래스를 나열 합니다.  
  
|클래스 이름|  
|----------------|  
|`Microsoft.VisualStudio.Package.Automation.OAProject`|  
|`Microsoft.VisualStudio.Package.Automation.OANavigableProjectItems`|  
|`Microsoft.VisualStudio.Package.Automation.OAProjectItems`|  
|`Microsoft.VisualStudio.Package.Automation.OAProjectItem`|  
|`Microsoft.VisualStudio.Package.Automation.OANestedProjectItem`|  
  
## <a name="properties-classes"></a>속성 클래스  
 다음 표에 프로젝트 형식 수 있게 해 주는 MPF의 클래스는 사용자가 탐색 하 고 속성 브라우저에서 수정할 수 있는 속성을 추가 합니다.  
  
|클래스 이름|  
|----------------|  
|`Microsoft.VisualStudio.Package.LocalizableProperties`|  
|`Microsoft.VisualStudio.Package.NodeProperties`|  
|`Microsoft.VisualStudio.Package.FileNodeProperties`|  
|`Microsoft.VisualStudio.Package.ProjectNodeProperties`|  
|`Microsoft.VisualStudio.Package.FolderNodeProperties`|  
|`Microsoft.VisualStudio.Package.ReferenceNodeProperties`|
