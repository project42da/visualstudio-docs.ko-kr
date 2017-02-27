---
title: "방법: 레지스트리 설정을 사용 하 여 개인 갤러리 관리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSIX 개인 갤러리, 관리"
  - "VSIX 개인 갤러리 관리"
ms.assetid: 86b86442-4293-4cad-9fe2-876eef65f426
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# 방법: 레지스트리 설정을 사용 하 여 개인 갤러리 관리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

관리자 또는 격리 된 셸 확장의 개발자 인 경우에 컨트롤, 템플릿 및 Visual Studio 갤러리, 샘플 갤러리 또는 개인 갤러리의 도구에 대 한 액세스를 제어할 수 있습니다. 사용 가능 여부가 갤러리 있도록 수정 된 레지스트리 키와 해당 값에 설명 하는.pkgdef 파일을 만듭니다.  
  
## 개인 갤러리 관리  
 갤러리에 여러 컴퓨터에 대 한 액세스를 제어 하는.pkgdef 파일을 만들 수 있습니다. 이 파일에는 다음 형식을 이어야 합니다.  
  
```  
[$RootPath$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) … MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom Feed|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 `Repositories` 갤러리를 활성화 또는 비활성화를 의미 합니다. Visual Studio 갤러리 및 샘플 갤러리는 다음과 같은 저장소 Guid를 사용합니다.  
  
-   Visual Studio 갤러리: 0F45E408\-7995\-4375\-9485\-86B8DB553DC9  
  
-   샘플 갤러리: AEB9CB40\-D8E6\-4615\-B52C\-27E307F8506C  
  
 `Disabled` 값은 선택 사항입니다. 기본적으로 갤러리 사용 됩니다.  
  
 `Priority` 값 옵션 대화 상자에서 나열 된 갤러리의 순서를 결정 합니다. Visual Studio 갤러리 우선 순위 10 개이고 샘플 갤러리의 우선 순위가 20입니다. 개인 갤러리 우선 순위가 100부터 시작합니다. 표시 되는 순서는 지역화 된 값으로 결정 됩니다 여러 갤러리에 동일한 우선 순위 값이 있으면 `DisplayName` 특성입니다.  
  
 `Protocol` Atom 또는 SharePoint 기반 갤러리에 값이 필요 합니다.  
  
 하거나 `DisplayName`, 또는 둘 다 `DisplayNameResourceID` 및 `DisplayNamePackageGuid`, 를 지정 해야 합니다. 모든 지정 된 경우는 `DisplayNameResourceID` 및 `DisplayNamePackageGuid` 쌍을 사용 합니다.  
  
## .Pkgdef 파일을 사용 하 여 Visual Studio 갤러리를 사용 하지 않도록 설정  
 .Pkgdef 파일에서 갤러리를 비활성화할 수 있습니다. 다음 항목은 Visual Studio 갤러리를 비활성화합니다.  
  
```  
[$RootPath$\ExtensionManager\Repositories\{0F45E408-7995-4375-9485-86B8DB553DC9}]  
"Disabled"=dword:00000001  
  
```  
  
 다음 항목 샘플 갤러리를 비활성화합니다.  
  
```  
[$RootPath$\ExtensionManager\Repositories\{AEB9CB40-D8E6-4615-B52C-27E307F8506C}]  
"Disabled"=dword:00000001  
  
```  
  
## 참고 항목  
 [개인 갤러리](../extensibility/private-galleries.md)