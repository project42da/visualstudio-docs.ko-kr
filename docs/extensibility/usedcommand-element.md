---
title: "UsedCommand 요소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UsedCommands element (VSCT XML schema)
- VSCT XML schema elements, UsedCommands
ms.assetid: 99cd05d3-644a-42ff-b289-8458cd1b20c0
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 06375b45e21e0b83c62f2509d666b786479ff2b4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="usedcommand-element"></a>UsedCommand 요소
다른.vsct 파일에 정의 된 명령에 액세스 하기 위해 VSPackage를 수 있습니다. 예를 들어 VSPackage는 표준을 사용 하 여 **복사** 문자로 정의 되는 명령에서 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셸 명령을 추가할 수 있습니다는 메뉴 또는 도구 모음을 다시 구현 하지 않고도 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<UsedCommand guid="guidMyCommandGroup" id="MyCommand" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|guid|필수. 명령을 식별 하는 GUID ID 쌍의 GUID입니다.|  
|ID|필수. 명령을 식별 하는 GUID ID 쌍의 ID입니다.|  
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|없음||  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[UsedCommands 요소](../extensibility/usedcommands-element.md)|UsedCommand 요소 그룹 및 다른 UsedCommands 그룹화 합니다.|  
  
## <a name="remarks"></a>설명  
 에 명령을 추가 하 여는 `<UsedCommands>` 요소, VSPackage 알립니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage 명령이 필요 하다는 환경입니다. 추가 해야는 `<UsedCommand>` 요소 패키지에 필요한 모든 명령에 대 한 모든 버전 및 Visual Studio의 구성에 포함 되어 있지 않습니다. 예를 들어 패키지는 Visual c + +에만 적용 되는 명령의 호출할 경우 명령이 제공 됩니다 Visual Web Developer의 사용자에 게 포함 하지 않으면는 `<UsedCommand>` 명령에 대 한 요소입니다.  
  
## <a name="example"></a>예  
  
```  
<UsedCommands>  
  <UsedCommand guid="guidVSStd97" id="cmdidCut"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidCopy"/>  
  <UsedCommand guid="guidVSStd97" id="cmdidPaste"/>  
</UsedCommands>  
```  
  
## <a name="see-also"></a>참고 항목  
 [UsedCommands 요소](../extensibility/usedcommands-element.md)   
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)