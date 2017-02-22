---
title: "일반적으로 프로젝트를 확장 하는 데 사용 되는 개체에 대 한 Catid | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage를 Catid"
  - "Guid, Vspackage"
  - "Catid VSPackages에 대 한"
ms.assetid: 0c7fdb66-ed96-4b36-89f6-021bca573572
caps.latest.revision: 16
caps.handback.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
---
# 일반적으로 프로젝트를 확장 하는 데 사용 되는 개체에 대 한 Catid
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 표에서 확장 하는 데 사용 되는 Catid `Project` 및 `ProjectItem` 자동화 개체에 대 한 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], 및 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트입니다.  이러한 Catid는 Vslangproj.olb에서 정의 됩니다.  
  
## Catid를 나열합니다.  
  
|Name|GUID|  
|----------|----------|  
|<xref:VSLangProj.PrjCATID.prjCATIDProject>|{610D4614\-D0D5\-11D2\-8599\-006097C68E81}|  
|<xref:VSLangProj.PrjCATID.prjCATIDProjectItem>|{610D4615\-D0D5\-11D2\-8599\-006097C68E81}|  
  
## Visual Basic Catid  
 다음 표에서 확장 하는 데 사용 되는 Catid [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 개체를 찾습니다.  모든 Vslangproj.olb에 정의 됩니다.  
  
|Name|GUID|  
|----------|----------|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBProjectBrowseObject>|{E0FDC879\-C32A\-4751\-A3D3\-0B3824BD575F}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBProjectConfigBrowseObject>|{67F8DD11\-14EB\-489b\-87F0\-F01C52AF3870}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBFileBrowseObject>|{EA5BD05D\-3C72\-40A5\-95A0\-28A2773311CA}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBFolderBrowseObject>|{932DC619\-2EAA\-4192\-B7E6\-3D15AD31DF49}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDVBReferenceBrowseObject>|{2289B812\-8191\-4e81\-B7B3\-174045AB0CB5}|  
  
## Visual C\# Catid  
 다음 Catid를 사용 하 여 확장할 수 있습니다 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 개체를 찾습니다.  모든 Vslangproj.olb에 정의 됩니다.  
  
|Name|GUID|  
|----------|----------|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpProjectBrowseObject>|{4EF9F003\-DE95\-4d60\-96B0\-212979F2A857}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpProjectConfigBrowseObject>|{A12CE10A\-227F\-4963\-ADB6\-3A43388513CA}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpFileBrowseObject>|{8D58E6AF\-ED4E\-48B0\-8C7B\-C74EF0735451}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpFolderBrowseObject>|{914FE278\-054A\-45DB\-BF9E\-5F22484CC84C}|  
|<xref:VSLangProj.PrjBrowseObjectCATID.prjCATIDCSharpReferenceBrowseObject>|{2F0FA3B8\-C855\-4a4e\-95A5\-CB45C67D6C27}|  
  
## C \+ \+ Catid  
 다음 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트 시스템 Catid를 형식 라이브러리에서 노출 되지 않습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .Net 및 이러한 프로젝트 개체를 확장할 때마다 코드에 포함 될 수 있습니다.  이러한 Catid에서 이후 버전의 형식 라이브러리에 포함 될 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
|Name|GUID|  
|----------|----------|  
|`CVCProjectNode`|{EE8299CB\-19B6\-4f20\-ABEA\-E1FD9A33B683}|  
|`CVCFolderNode`|{EE8299CA\-19B6\-4f20\-ABEA\-E1FD9A33B683}|  
|`CVCFileNode`|{EE8299C9\-19B6\-4f20\-ABEA\-E1FD9A33B683}|  
  
 다음 코드 예제에서는 코드에서 이러한 Catid를 프로그래밍 하는 방법을 보여 줍니다.  
  
```  
const LPOLESTR CVCProjectNode::s_wszCATID = L"{EE8299CB-19B6-4f20-ABEA-E1FD9A33B683}";  
const LPOLESTR CVCFolderNode::s_wszCATID = L"{EE8299CA-19B6-4f20-ABEA-E1FD9A33B683}";  
const LPOLESTR CVCFileNode::s_wszCATID = L"{EE8299C9-19B6-4f20-ABEA-E1FD9A33B683}";  
```  
  
 다음 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트 시스템 Catid도 노출 되지 않습니다 형식 라이브러리에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .Net 및 이러한 프로젝트 개체를 확장할 때마다 코드에 포함 될 수 있습니다.  이러한 Catid만 사용할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] .NET 2003와의 이후 릴리스에서 사용할 수 없습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
|Name|GUID|  
|----------|----------|  
|`CVCAssemblyReferenceNode` **:**|{FE8299C9\-19B6\-4f20\-ABEA\-E1FD9A33B683}|  
|`CVCProjectReferenceNode`|{593DCFCE\-20A7\-48e4\-ACA1\-49ADE9049887}|  
|`CVCActiveXReferenceNode`|{9E8182D3\-C60A\-44f4\-A74B\-14C90EF9CACE}|  
|`CVCReferences`|{FE8299CA\-19B6\-4f20\-ABEA\-E1FD9A33B683}|  
  
 다음 코드 예제에서는 코드에서 이러한 Catid를 프로그래밍 하는 방법을 보여 줍니다.  
  
```  
const LPOLESTR CVCAssemblyReferenceNode::s_wszCATID = L"{FE8299C9-19B6-4f20-ABEA-E1FD9A33B683}";  
const LPOLESTR CVCProjectReferenceNode::s_wszCATID = L"{593DCFCE-20A7-48e4-ACA1-49ADE9049887}";  
const LPOLESTR CVCActiveXReferenceNode::s_wszCATID = L"{9E8182D3-C60A-44f4-A74B-14C90EF9CACE}";  
const LPOLESTR CVCReferences::s_wszCATID = L"{FE8299CA-19B6-4f20-ABEA-E1FD9A33B683}";  
```  
  
 에 대 한 Guid는 [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 프로젝트 형식이 다음 표에 표시 됩니다.  
  
|프로젝트 형식|GUID|  
|-------------|----------|  
|[!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)]|{FAE04EC0\-301F\-11D3\-BF4B\-00C04F79EFBC}|  
|[!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)]|{F184B08F\-C81C\-45F6\-A57F\-5ABD9991F28F}|  
  
## 참고 항목  
 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)