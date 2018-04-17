---
title: ButtonText 요소 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- ButtonText element (VSCT XML schema)
- VSCT XML schema elements, ButtonText
ms.assetid: 56aba884-0356-4894-ae4e-32d3938f6865
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 2fca0fbb22bf51353eeaa64f519face53bfb23c8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="buttontext-element"></a>ButtonText 요소
이 필드를 사용 하면 다양 한 메뉴에 표시 되는 텍스트를 지정할 수 있습니다. 기본적으로는 `ButtonText` 요소 메뉴 컨트롤러에 나타납니다. `ButtonText` 다른 텍스트 필드가 비어 있으면도 요소의 기본값이 됩니다. `ButtonText` 다른 텍스트 필드가 지정 된 경우에 요소를 비워 둘 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
<ButtonText>My Command</ButtonText>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Strings 요소](../extensibility/strings-element.md)|와 같은 텍스트 요소를 그룹화 `ButtonText` 및 `CommandName`합니다.|  
  
## <a name="text-value"></a>텍스트 값  
 텍스트 값은 `ButtonText` 요소 메뉴 항목, 바로 가기 단축키 +, 및 표시 되는 텍스트에 있는 다른 사용자 인터페이스 (UI) 요소에 대해 표시 되는 텍스트를 제공 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)