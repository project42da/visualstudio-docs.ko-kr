---
title: "BscMake 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.task.bscmake
- VC.Project.VCBscMakeTool.PreserveSBR
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), tasks
- BscMake task (MSBuild (Visual C++))
ms.assetid: bb98fc67-cad8-43a7-9598-60df6d734db2
caps.latest.revision: 7
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
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
translationtype: Human Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 7522b540558794c702fc5a49972a9e00f785fd2f
ms.lasthandoff: 04/05/2017

---
# <a name="bscmake-task"></a>BscMake 작업
> [!IMPORTANT]
>  bscmake는 더 이상 Visual Studio IDE에서 사용되지 않습니다. Visual Studio 2008부터 찾아보기 정보는 솔루션 폴더의 .sdf 파일에 자동으로 저장됩니다.  
  
 Microsoft Browse Information Maintenance Utility 도구(bscmake.exe)를 래핑합니다.  bscmake.exe 도구는 컴파일하는 동안 만들어진 소스 브라우저 파일(.sbr)에서 찾아보기 정보 파일(.bsc)을 빌드합니다. **개체 브라우저**를 사용하여 .bsc 파일을 볼 수 있습니다. 자세한 내용은 [BSCMAKE 참조](/cpp/build/reference/bscmake-reference)를 참조하세요.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 **BscMake** 작업의 매개 변수에 대해 설명합니다. 대부분의 작업 매개 변수는 명령줄 옵션에 해당합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|**AdditionalOptions**|선택적 **String** 매개 변수입니다.<br /><br /> 명령줄에 지정된 것처럼 옵션 목록입니다. 예를 들어 "/*option1* /*option2* /*option#*"과 같습니다. 이 매개 변수를 사용하여 다른 **BscMake** 작업 매개 변수로 표현되지 않는 옵션을 지정합니다.<br /><br /> 자세한 내용은 [BSCMAKE 옵션](/cpp/build/reference/bscmake-options)의 옵션을 참조하세요.|  
|**OutputFile**|선택적 **문자열** 매개 변수입니다.<br /><br /> 기본 출력 파일 이름을 재정의하는 파일 이름을 지정합니다.<br /><br /> 자세한 내용은 [BSCMAKE 옵션](/cpp/build/reference/bscmake-options)의 **/o** 옵션을 참조하세요.|  
|**PreserveSBR**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 비증분 빌드를 수행합니다. 전체 비증분 빌드는 .bsc 파일이 있는지 여부에 관계 없이 발생하고 .sbr 파일이 잘리지 않도록 방지합니다.<br /><br /> 자세한 내용은 [BSCMAKE 옵션](/cpp/build/reference/bscmake-options)의 **/n** 옵션을 참조하세요.|  
|**Sources**|선택적 **ITaskItem[]** 매개 변수입니다.<br /><br /> 작업에서 사용하고 내보낼 수 있는 MSBuild 소스 파일 항목의 배열을 정의합니다.|  
|**SuppressStartupBanner**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 작업을 시작할 때 저작권과 버전 번호 메시지가 표시되지 않도록 합니다.<br /><br /> 자세한 내용은 [BSCMAKE 옵션](/cpp/build/reference/bscmake-options)의 **/NOLOGO** 옵션을 참조하세요.|  
|**TrackerLogDirectory**|선택적 **String** 매개 변수입니다.<br /><br /> 추적기 로그용 디렉터리를 지정합니다.|  
  
## <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [작업 참조](../msbuild/msbuild-task-reference.md)