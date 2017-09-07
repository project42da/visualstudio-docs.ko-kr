---
title: "방법: 레지스트리 설정을 사용 하 여 전용 갤러리를 사용 하는 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSIX private galleries, managing
- managing VSIX private galleries
ms.assetid: 86b86442-4293-4cad-9fe2-876eef65f426
caps.latest.revision: 6
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
ms.translationtype: MT
ms.sourcegitcommit: 8ce054bf6149f0224785f4c3cd9274e86dc09d04
ms.openlocfilehash: 00c42a4dbd6a9a526d661b7fa04793d531acd8bc
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="how-to-manage-a-private-gallery-by-using-registry-settings"></a>방법: 레지스트리 설정을 사용 하 여 전용 갤러리를 관리 합니다.
격리 셸 확장의 개발자 또는 관리자 인 경우에 컨트롤, 템플릿 및 Visual Studio 갤러리, 샘플 갤러리 또는 전용 갤러리의 도구에 대 한 액세스를 제어할 수 있습니다. 사용 가능 여부가 갤러리는 하 게 하려면 수정 된 레지스트리 키와 해당 값을 설명 하는.pkgdef 파일을 만듭니다.  
  
## <a name="managing-private-galleries"></a>전용 갤러리를 관리합니다.  
 갤러리에 여러 컴퓨터에 대 한 액세스를 제어 하도록.pkgdef 파일을 만들 수 있습니다. 이 파일에는 다음 형식을 이어야 합니다.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{UniqueGUID}]  
@={URI}  (REG_SZ)  
Disabled=0 | 1 (DWORD)  
Priority=0 (highest priority) ... MaxInt (lowest priority) (DWORD) (uint)  
Protocol=Atom Feed|Sharepoint (REG_SZ)  
DisplayName={DisplayName} (REG_SZ)  
DisplayNameResourceID={ID} (REG_SZ)  
DisplayNamePackageGuid={GUID} (REG_SZ)  
  
```  
  
 `Repositories` 을 사용 하거나 사용 하지 않도록 설정 갤러리에 키가 참조 합니다. Visual Studio 갤러리 및 샘플 갤러리 Guid는 다음 저장소를 사용합니다.  
  
-   Visual Studio 갤러리: 0F45E408-7995-4375-9485-86B8DB553DC9  
  
-   샘플 갤러리: AEB9CB40-D8E6-4615-B52C-27E307F8506C  
  
 `Disabled` 값은 선택 사항입니다. 기본적으로 갤러리 사용 됩니다.  
  
 `Priority` 옵션 대화 상자에서 나열 된 갤러리의 순서를 결정 하는 값입니다. Visual Studio 갤러리 우선 순위 10 개이고 샘플 갤러리의 우선 순위가 20입니다. 전용 갤러리 우선 순위가 100부터 시작합니다. 표시 되는 순서는 지역화 된 값에 의해 결정 됩니다 여러 갤러리 동일한 우선 순위 값이 있으면 `DisplayName` 특성입니다.  
  
 `Protocol` Atom 또는 SharePoint 기반 갤러리에 값이 필요 합니다.  
  
 중 하나 `DisplayName`, 또는 둘 다 `DisplayNameResourceID` 및 `DisplayNamePackageGuid`를 지정 해야 합니다. 모든 지정 되어 있으면 하면 `DisplayNameResourceID` 및 `DisplayNamePackageGuid` 쌍을 사용 합니다.  
  
## <a name="disabling-the-visual-studio-gallery-using-a-pkgdef-file"></a>.Pkgdef 파일을 사용 하 여 Visual Studio 갤러리를 사용 하지 않도록 설정  
 .Pkgdef 파일에서 갤러리를 비활성화할 수 있습니다. 다음 항목은 Visual Studio 갤러리를 비활성화합니다.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{0F45E408-7995-4375-9485-86B8DB553DC9}]  
"Disabled"=dword:00000001  
  
```  
  
 다음 항목 샘플 갤러리를 비활성화합니다.  
  
```  
[$RootKey$\ExtensionManager\Repositories\{AEB9CB40-D8E6-4615-B52C-27E307F8506C}]  
"Disabled"=dword:00000001  
  
```  
  
## <a name="see-also"></a>참고 항목  
 [전용 갤러리](../extensibility/private-galleries.md)
